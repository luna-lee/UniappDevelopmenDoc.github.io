#  moon-swiper-action
### 作者：闰月飞鸟；时间：2021/01/17
### 开发目的
- u-swiper-action 在table组件中渲染有性能问题。故重写之
- 列表左滑展示操作区域
- 每次滑动将之前的关闭再展示本次的

### 设计思路
-  以scroll-view为基础组件，通过设置主体视图宽度和操作视图宽度，以及判断滑动状态，打开/关闭来控制其他滑块的关闭


### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
list|列表数据|Array|---|[]
actionWidth|操作视图宽度|Number|---|200
contentWidth|主题视图宽度|Number|---|700


### Methods

方法 |说明|参数|返回值
---|---|---|---
closeAll|关闭所有滑块,由于关闭有延时,这里返回的是一个promis，调用的时候需要，用await|--|--

### slot-scope
名称 |说明
---|---
index | 当前遍历列表的下标  使用时注意: <font color="red">小程序中 父组件slot的元素上必须加上slot-scope="{ lock }" 不然选不出来</font>
item | 当前遍历列表的对象  使用时注意: <font color="red">小程序中 父组件slot的元素上必须加上slot-scope="{ lock }" 不然选不出来</font>