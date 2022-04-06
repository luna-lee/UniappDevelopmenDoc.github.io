
#  service-checkbox 
### 作者：闰月飞鸟；时间：2020/03/21
### 开发目的
- 封装moon-checkbox-group组件，依据字典值，自动渲染。
### 设计思路
-  获取，拆分，触发返回


### Props 

参数 |说明|类型|可选值|默认值
---|---|---|---|---
moon-checkbox-group所有属性|--|--|--|--
code|字典值|String Number|——|——
cascadeLevel|字典参数|String|——|——
pCode|字典参数|String|——|——
value4.sync|接收返回label|String|——|——
wrap|是否每个checkbox占一行|Boolean|——|false
inputAlign| 当wrap为false时，内容显示的位置|String|left center right| left
outsideList|外部出入的数据源|Array|———|null
option|数据源对应格式|Object|———|{value: 'id', label: 'value', disabled: 'disabled'}
filterValue|过滤选项所对应的value值|Array|——|[] 



 


 

