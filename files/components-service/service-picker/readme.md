#  service-picker
### 作者：闰月飞鸟；时间：2020/06/2
### 更新日志  2020/06/27
- 应moon-picker 的修改而修改。采用uView样式
### 开发目的
- 封装moon-picker组件，依据字典值，自动获取下拉选择器的填充数据，并将选择器的触发和返回值展示input组件上，同时将选中的值作为事件返回给父组件。
### 设计思路
- 组件初始化时即调用接口，依据code获取数据字典并填充到选择器组件中。   为统一字体风格，这里统一用moon-input组件来展示选择器所选择的数据。同时用于触发开启选择器。 


### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
mode|u-select中的mode |——|——|——
option|moon-picker组件中的option，默认值改变 |Object|——|{label: 'value',	value: 'id',id: 'id',children: 'children',parentId: 'parentId'}
value/v-model| 绑定值，联动选择->type==string为逗号拼接的字符串，type==array为第一列的value|String|——|""
value1/:value1.sync| 绑定值，联动选择type==array为为第二列的value|String|——|""
value2/:value2.sync| 绑定值，联动选择type==array为为第三列的value|String|——|""
value4|接收返回label|String|——|——
code|字典值|String|——|——
dynamicID|动态字典表ID|String|——|——
cascadeLevel|字典参数|String|——|——
pCode|字典参数|String|——|——
inputAlign|u-input 属性|String|center / right|left
rightIcon|右侧图标|String|——|arrow-right
type|接收返回数据的模式，string 为字符串逗号拼接， array将结果为分别返回给value，value1，value2|String|string/array|string
disabled|禁用|Boolean|——|false
placeholder|占位符号|String|——|请选择
filterValue|过滤选项所对应的value值|Array|——|[]
showTag|当为单联模式时即mode=='single-column'，且showTag为true，则以tag标签形式展示|Boolean|——|true
tagIsRadio|当showTag为true且tagIsRadio为true，则以radio显示|Boolean|——|fasle
tagTitle|当 以tag标签形式展示时的标题|String|——|""
outsideList|外部传入数据源，若code为falsely则使用该数据源|Array|——|[]
multiple|当 以tag标签形式展示时设置多选单选|Boolean|true，false|false
topQuery|顶部查询样式|Boolean|true，false|false
noDataText|数组为空时，显示的提示语|String|-| 暂无数据
 cache|是否优先从缓存获取数据|Boolean|true/false| true
###  Slot
名称 |说明
---|---
default | 自定义触发打开面板样式，并接收用域参数inputValue,show
 