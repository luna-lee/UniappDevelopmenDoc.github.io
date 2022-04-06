#  service-dynamic-form
### 作者：闰月飞鸟；时间：2020/08/18
### 开发目的
- 依据后端配置的动态表单参数，自动生成对应的表单页面

### 设计思路
-  以sel-dynamic-form为基础组件及后端传递过来的表单参数，动态渲染页面

### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
entityName|当前动态表单业务对应的表单实例名|String|---|必传
outPushData|外部调用接口，将structureTableFieldDTOList entityModel 传入。只有在entityName为空时才使用 |{}|---|{structureTableFieldDTOList: [],entityModel: {}}
businessId|动态表单所关联的业务businessId，新增时需要将该属性值追加到保存对象中。|String|---|""
id|动态表单所关联的业务id，新增时需要将该属性值追加到保存对象中。 与bussinessId互斥|String|---|""
defaultEntityModel|设置entityModel默认属性值|Object|---|{}
labelWidth|Form Props label宽度|String, Number|---|40%
labelPosition|Form Props label位置,若组件单独设置了,则被覆盖|String|top/left| left
labelAlign|Form Props label的对齐方式,若组件单独设置了,则被覆盖|String |center / right|left
disabled|组件是否可用,app,h5端 组件中配置了disabled会覆盖改值|Boolean|--|false
inputAlign|表单中输入框文字的对齐方式，若组件中自定了inputAlign这覆盖该值，若moon-input中的type为textarea，则设置无效，|String|left，right|right
collapse|开启折叠视图|Boolean|--|false
workflow|关联到工作流，需要将表单内容每次的变化都存入store里，并且在保存的时候保存外部传入的表单数据|Boolean|--|false
saveInterface|保存接口名称,取dynamic接口下的方法名|String|--|dynamicSaveAll
showLoading|请求接口是弹出提示信息！|Boolean|--|true
 
### Events
方法 |说明|参数|返回值
---|---|---|---
update:loading|将当前loading状态返回,当页面中有多个动态表单时，在父组件中对其状态进行统一判断。如提示加载信息，其他组件的高度重新计算等等|--|--
change|返回内部entityModel|--|--

 
### Methods
方法 |说明|参数|返回值
---|---|---|---
onSubmit|动态表单保存方法|wfFormEntity = {}, extraObj = {}|若是与工作流关联，则保存的时候，实例取外部传入的实体.extraObj额外对象属性
validateForm|表单列表校验,返回校验结果。当外部由多个表单列表构成时，需要整体校验，则调用每个表单列表中的该方法|--|--
 