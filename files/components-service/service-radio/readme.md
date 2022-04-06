
#  service-radio 
### 作者：闰月飞鸟；时间：2020/03/21
### 开发目的
- 封装u-radio-group组件，依据字典值，自动渲染。
### 设计思路
-  获取，拆分，触发返回

### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
u-radio-group所有属性|--|--|--|--
code|字典值，必填|String Number|——|——
value4.sync|接收返回label|String|——|——
outsideList|外部传入数据源，若code为falsely则使用该数据源|Array|——|[]
filterValue|过滤选项所对应的value值|Array|——|[]


 ### Events 
名称 |说明 
---|--- 
update:value4|返回所选项对应字典的label值，多选返回逗号隔开的字符串 
update:slectedLabel|返回所选项对应字典的label值，多选返回逗号隔开的字符串 