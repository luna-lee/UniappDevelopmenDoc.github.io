#  moon-click

### 作者：闰月飞鸟；时间：2020/05/14
### 开发目的
- 封装元素点击事件，避免元素重复点击触发事件。如button点击事件，按钮页面跳转等。
### 设计思路
- 通过设置lock，第一次点击后设置为true，延时500ms后变成false，按钮只有在为false时触发才有效果 。这样可以给页面切换，组件渲染留出时间
- 通过作用域插槽将lock返回给slot中具体的组件，


### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
duration|锁定时间|Number|--|500 
scoped|是否将lock状态传入slot-scope中|Boolean|--|false
disabled|组件是否可用|Boolean|--|false

###  Slot
名称 |说明
---|---
default | dom元素 <font color="red">当slot作用域中是第三方组件时，组件的引入只能通过import+component的方式引入，esycom引入不会渲染</font>

### slot-scope
名称 |说明
---|---
lock | 当前锁定状态,只有scoped为true时才传入，使用时注意: <font color="red">小程序中 父组件slot的元素上必须加上slot-scope="{ lock }" 不然选不出来</font>

###  Events
名称 |说明| 参数
---|---|---|
click|点击事件|——
 
 ```
 <moon-click @click="onTap" scoped>
	<button   slot-scope="{ lock }" type="primary" :disabled="lock">ddd</button>
 </moon-click>
 ```


 

