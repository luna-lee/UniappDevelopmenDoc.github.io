#   service-select-tree

### 作者：闰月飞鸟；时间：2020/05/21
### 开发目的
-   封装moon-select-tree与字典获取数据方法。
### 设计思路
 - 传入字典参数，调用接口返回树数据。 调用moon-selelct-tree组件渲染。
 
### Props 

参数 |说明|类型|可选值|默认值
---|---|---|---|---
value/v-model|接收返回数据ID|String|—| ""
moon-selelct-tree所有属性|-|-|—|-
code|字典值|String|—| ""
dynamicID|动态字典表ID|String|——|——
cascadeLevel|字典参数|String|——|——
pCode|字典参数|String|——|——
filterValue|筛选出指定id的项及子项目|String|——|——
filterExceptValue|排除指定id项及子项，多个用逗号隔开|String|——|——
unitUser|单位人员树形选择器|Boolean|—| false
unitUserParams|unitUser数据接口参数|Object|—| {pId: ''}
eventType|事件类型树形选择器|Boolean|—| false
gridUser|网格员列表|Boolean|—| false
gridUserExceptFour|网格员列表，排除4级|Boolean|—| false
gridUserParams|网格人员数据参数 ，默认网格员 4001_FOUR|Object|—| { gridTypeCode: '4001_FOUR' }
department|部门列表|Boolean|—| false
departmentParams|部门数据参数 |Object|—| { unitStatus: '1006_NORMAL' }
gridList|网格列表|Boolean|—| false
value1|通过sync额外绑定的接收返回数据|String|—| ""
value2|通过sync额外绑定的接收返回数据|String|—| ""
value3|通过sync额外绑定的接收返回数据|String|—| ""
value4|通过sync额外绑定的接收返回数据|String|—| ""
extraValueOption|额外绑定的数据的属性配置，指定接收所选对象中的具体的属性名。只有设置了指定返回属性值，额外绑定的值才能接收到数据。即配置输入|Object|—| {	value1: '', value2: '',value3: '',value4: '' }
mode|触发组件名|String|label/tag| “tag”
title|popup面板标题|String|—| "请选择"
disabled|组件是否可用|Boolean|true/false| false
inputAlign|mode为label时，内容的展示方式|String|left center right| left
canSelectParentNode|父节点可以点击，为true时 只能点击展开图标展开子节点|Boolean|true/false| false;
topQuery|必须在mode为label时才有用，用于动态查询条件构建顶部查询样式|Boolean|true，false|false
 


###  Slot
名称 |说明
---|---
add-icon |自定义新增图标
label|当mode为lable时，触发及展示样式。默认为moon-input

 ```javascript
 //额外值的返回在动态表单中的配置方式
 {
 	entityFieldName: 'projectContact',
 	label: '项目对接人姓名',
 	componentName: 'service-select-tree',
 	value1: 'projectContactPhone',//指定接收属性名
 	componentOption: {
 		unitUser: true,
 		extraValueOption: {
 		  value1: 'pId'  // 额外属性名，以及其返回值,在数据源对象中对应的属性名。
 		}
 	},
 	required: true,
 	rule: [{
 		required: true,
 		message: '请选择“接待人员”',
 		trigger: ['blur', 'change']
 	}]
 },
 
 ```

