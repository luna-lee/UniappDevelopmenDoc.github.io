#  sel-dynamic-form
### 作者：闰月飞鸟；时间：2020/07/06
### 开发目的
- 依据表单配置，动态生成表单，提交统一校验
- 使用过程中可以使用默认布局也可以自定义布局。如一行多个，或label上下居中等等

### 设计思路
-  只做构造器，不与后台交互
-  输入：表单的构造单元属性，各个属性对应展示的形式。
-  属性以组件的形式展示，当后端传递的是组件编码，需要在父组件将对应的组件名配置好再传入
-  属性对应的组件都以v-model进行传赋值
-  通过sync修饰符额外扩展了4个双向绑定属性:value1,value2,value3,value4。用与适配组件同时返回多个值，且都需要绑定到entityModel对象上时使用。
-  同时需要在目标组件上做兼容处理，除了$emit('xx')还需要将其数据$emit('update:value?')
-  利用flex-wrap动态依据不同组件设置的宽度，达到一行展示多个表单组件

### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
structureFieldDTOList|表单结构对象数组|Array[Object]|---|必传，格式见下
entityModel/:entityModel.sync|实体对象,若为null或{}，则从structureFieldDTOList中自行构造出一个实体模型|Object|---| --
formItemWidth|FormItem的宽度，通过该属性可以设置单行显示的个数|String|---| 100%
labelWidth|Form Props label宽度|String, Number|---|40%
labelStyle|Form Props 若组件单独设置了labelStyle则被覆盖|Object|---|{}
labelPosition|Form Props label位置,若组件单独设置了,则被覆盖|String|top/left| left
labelAlign|Form Props label的对齐方式,若组件单独设置了,则被覆盖|String |center / right|left
errorType|Form Props 错误的提示方式，数组形式,若组件单独设置了,则被覆盖|Array|['message','none','border-bottom','border','toast']|['message']
disabled|组件是否可用,app,h5端 组件中配置了disabled会覆盖改值|Boolean|--|false
inputAlign|表单中输入框文字的对齐方式，若组件中自定了inputAlign这覆盖该值，若moon-input中的type为textarea，则设置无效，|String|left，top|left
slotPosition|插糟所在的位置，从0开始计数。先渲染插槽，接着渲染组件|Number|--|0
slotLocation|插糟相对于当前行的位置，上面/下面|String|--|top
slotCollapse|开启slot点后收缩后续项目,即折叠 |Boolean|--|false
rules|Form校验规则。使用时会与structureFieldDTOList中的规则合并，优先级低|Object|---|{}

### Slot
名称 |说明
---|---
default|显示在slotPosition指定的位置，当slotCollapse为true时，则在点击的时候折叠收起后续项目。同时通过slotscope将折叠状态collapseShow返回 同时也将当前的inner_entityModel值用entity接收返回，slotscope注意在小程序中的使用




### Methods

方法 |说明|参数|返回值
---|---|---|---
onSubmit|方式一:直接传入Function， 校验成功后执行传入的函数 。方式二：校验成功后将当前inner_entityModel返回,校验失败则返回false,提交服务器的时候需要自行判断返回值|Function,其参数为inner_entityModel|--
~~setRules~~|~~当rules中包含函数，且为小程序环境， <font color="red">则需要外部通过ref调用改方法</font>~~|~~构造对象structureFieldDTOList~~|--
validateForm|表单校验,返回校验结果。当外部由多个form表单构成时，需要整体校验，则调用每个form中的该方法|--|--

```javascript
	onSubmit() {
		<!-- 方式一 -->
			this.$refs.dynamicForm.onSubmit(function(entityModel) {
				console.log(JSON.stringify(entityModel));
				console.log(JSON.stringify('执行具体业务的表单保存操作'));
			});
		<!-- 方式二 -->
		let entityModel=this.$refs.dynamicForm.onSubmit();
		if(entityModel)
		{
			console.log(JSON.stringify(entityModel));
			console.log(JSON.stringify('执行具体业务的表单保存操作'));}
		}
```

### structureFieldDTOList 格式
``` javascript
[
				{
					//属性单元名称 注意不能有空格
					entityFieldName: 'name', 
					//额外的双向绑定属性。可以不传
					value1:"",
					value2:"",
					value3:"",
					value4:"",
					/* 当label为falsely时 labelwidth为 0 ,required 星号不显示，但可以校验，formItemRigth独占整行 */
					label: '姓名',
					//指定用于展示的组件
					componentName: 'moon-input',
					/* 可以选属性， 这些属性都能通过props设置在form上，也能针对单个设置。参考uview文档 */
					width: '50%',//设置控件宽度，会覆盖formItemWidth值
					labelPosition: 'left',
					labelWidth: '40%',
					labelAlign: 'left',
					labelStyle:{},
					rightIcon: '',
					leftIcon: '',
					leftIconStyle: {},
					rightIconStyle: {},
					//组件其他的props属性 由于非App H5端不支持v-bind  故在小程序则需要在组件上指名具体的属性值
					componentOption: {
						disabled: true
						……
					},
					required:true,//只做展示是否显示左边的"*"号，若要提交校验则配置rule即可
					//属性单元的  校验规则，参考uview中form的校验
					//当rules中有函数时该方法只适用于App H5 ,而小程序需要在外部通过ref调用setRules方法，传入具体的rules对象，参考uviewUI文档。若rules中没有函数则通用
					rule: [
						{
							required: true,
							message: '请输入姓名',
							// blur和change事件触发检验
							trigger: ['blur', 'change']
						}
					],
					//关联条件表达式。为适应复杂显隐条件和动态配置显隐条件而开发。
					//依据执行结果显示隐藏控件。表达式中判断属性前需要加$符，执行时会用this.inner_entityModel.替换。 
					isShow:"$a==0"
				}
			]
```
 

 


 



 


 

