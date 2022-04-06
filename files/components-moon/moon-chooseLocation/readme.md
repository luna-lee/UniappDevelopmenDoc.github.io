#  moon-chooseLocation
### 作者：闰月飞鸟；时间：2020/03/21
### 开发目的
- 封装地址选择chooseLocation方法， 
### 设计思路
- 由于一般业务中地点的存储都是分开存，经度纬度以及地址名，故这将返回值都进行双向绑定，这样便于业务中直接将对象属性绑定到组件上
- 对于v-model 则依据returnType类型 返回具体的地址名
- 由于该组件返回多个属性，为适配动态表单，需要将经度纬度 同时$emit('update:value1',longitude)$emit('update:value2',latitude)出去

### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
value/v-model| 绑定值为 地址|String|——|""
longitude| 经度 可以通过sync修饰符接收返回数据|String|——|""
value1|适配动态表单 经度 可以通过sync修饰符接收返回数据|String|——|""
latitude| 纬度 可以通过sync修饰符接收返回数据|String|——|""
value2|适配动态表单 纬度 可以通过sync修饰符接收返回数据|String|——|""
name|所选地标名字 可以通过sync修饰符接收返回数据|String|——|""
returnType|返回类型 all 名称+(地址), address地址，name 名称|String|——|"all"
inputAlign|u-input 属性|String|center / right|left
disabled|组件是否可用|Boolean|--|false
join|是否将地址与坐标合并返回|Boolean|--|false

 ###  Slot
名称 |说明
---|---
default | 右侧图标



 

