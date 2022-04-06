
# service-select-house
### 作者：闰月飞鸟；时间：2020/09/27
### 开发目的
- 造小区楼栋单元房屋级联选择器。
### 设计思路
- 点击异步调用接口，渲染出所对应的数据。
- 传入小区楼栋单元房屋各自所对应的id，并依据传入的id在对应的数据列中标记出所选对象。并将所有选中的对象都显示在显示区域。
- 只有在点击确定按钮后才将所选数据抛出。点击取消后，还原之前选择状态及数据。
- 模糊搜索小区，并保留当前有选中项。


### Props 

参数 |说明|类型|可选值|默认值
---|---|---|---|---
value/v-model| 房屋id。|String|——|""
communityId/:communityId.sync| 小区id |String|——|""
buildId/:buildId.sync| 楼栋id |String|——|""
unitId/:unitId.sync| 单元id |String|——|""
address/:address.sync| 地址中文名 |String|——|""
value1/:value1.sync| 小区id 适配动态表单 |String|——|""
value2/:value2.sync| 楼栋id 适配动态表单|String|——|""
value3/:value3.sync| 单元id 适配动态表单|String|——|""
value4/:value4.sync| 地址中文名 适配动态表单|String|——|""
inputAlign|u-input 属性|String|center / right|left
disabled|组件是否可用|Boolean|--|false
rightIcon|右侧图标|String|——|arrow-right
placeholder|占位符号|String|——|请选择地区
queryView|当前组件用于查询视图，默认false即必须选择全确定按钮才可用|Boolean|--|false

 
 
 ### Events 
名称 |说明 
---|--- 
selectHouse|返回所选房屋对象 


