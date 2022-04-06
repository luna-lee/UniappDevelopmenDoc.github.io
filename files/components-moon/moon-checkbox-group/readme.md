#  moon-checkbox
### 作者：闰月飞鸟；时间：2020/06/26
### 开发目的
- 封装的uniapp的checkbox,实现类似elementUI的checkbox，只需在group组件上双向绑定值即可。
- 同时对非未匹配到的值进行保留。
- 由于u-checkbox使用的是$parent方式查找，在微信小程序上渲染时，由于slot层级导致无法获取到 group组件。顾这里重写，采用provide方式。这个方式不使用支付宝小程序
### 设计思路
-  获取，监听，拆分，触发返回

### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
value/v-model| 绑定值，非checkbox值被保留下来|String|——|""
u-checkboxs所有属性| 统一设置| ——|——|——






 

 


 



 


 

