# moon-datetime

### 作者：闰月飞鸟；时间：2020/06/27
### 开发目的
- 重新封装uView的日期时间控件
- 统一输入输出。遵循dayjs的格式规范，如下表格
### 设计思路
- 通过设置日期格式，来推断面板内容

### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
 value/v-model|接收/设置默认的日期|——|——|——
 value1/:value1.sync|接收/设置结束的日期 配合动态表单|——|——|——
 endTime/:endTime.sync|接收/设置结束的日期|——|——|——
 dateFormat| 日期格式，依据格式展示具体的时间内容。|String|--|YYYY-MM-DD
 inputAlign|u-input 属性|String|center / right|left
 disabled|组件是否可用|Boolean|--|false
 defaultToday|true时，当value为空，则返回当天的日期时间|Boolean|--|false
 placeholder|提示占位字符|String|--|请选择时间
 title|顶部中间的标题|String|--|--.
 range |开启区间选择|Boolean|--|false
 moonStyle | moon组件自定义样式|Obj ect|——|{}
maxDate|最大选择日期|String|--|--
minDate|最小选择日期|String|--|--
judgeType|判断颗粒度，参考 https://dayjs.fenxianglu.cn/category/query.html#%E4%B9%8B%E9%97%B4|String|--|D

 ###  Slot
名称 |说明
---|---
default | 右侧图标



### dayjs格式规范
|Format	|Output				|Description					 
---|---|--- 
|YY		|18					|两位数的年份					|
|YYYY	|2018				|四位数的年份					|
|M		|1-12				|月份，从 1 开始				|
|MM		|01-12				|月份，两位数					|
|D		|1-31				|月份里的一天					|
|DD		|01-31				|月份里的一天，两位数			|
|H		|0-23				|小时							|
|HH		|00-23				|小时，两位数					|
|m		|0-59				|分钟							|
|mm		|00-59				|分钟，两位数					|
|s		|0-59				|秒								|
|ss		|00-59				|秒 两位数						|
 
 


 

