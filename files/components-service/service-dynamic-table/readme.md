#  service-dynamic-table
### 作者：闰月飞鸟；时间：2020/08/29
### 开发目的
- 依据后端配置的动态表单参数，自动生成对应的表格页面

### 设计思路
-  以sel-dynamic-table为基础组件及后端传递过来的表单参数，动态渲染页面


### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
entityName|当前动态表单业务对应的表单实例名|String|---|必传
businessId|动态表单所关联的业务id，新增时需要将该属性值追加到保存对象中。|String|---|""
value/v-model|实体对象数组，首次加载会依据entityName，businessId从服务端获取|Array|---|  []
labelWidth|Form Props label宽度|String, Number|---|40%
labelPosition|Form Props label位置,若组件单独设置了,则被覆盖|String|top/left| left
labelAlign|Form Props label的对齐方式,若组件单独设置了,则被覆盖|String |center / right|left
disabled|组件是否可用,app,h5端 组件中配置了disabled会覆盖改值|Boolean|--|false
inputAlign|表单中输入框文字的对齐方式，若组件中自定了inputAlign这覆盖该值，若moon-input中的type为textarea，则设置无效，|String|left，right|right
workflowItemShowConfig|工作流中表格单元显隐属性|Object|--|{}
showType|列表展示形式|String|table、card|"table"
 