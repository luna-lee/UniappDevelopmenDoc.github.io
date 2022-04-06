#  modify-u-popup
### 作者：闰月飞鸟；时间：2020/09/24
### 开发目的
- 修改uview-UI中组件，以更好的适用具体的业务
- 将u-popup的渲染方式由v-if改成v-show, 避免每次加载重新渲染。小程序下还是原来的组件
- 新增reload属性，用于需要每次打开都要重新渲染的情况。默认为false
- 由于u-popup的渲染使用了scroll-view造成 内部再次渲染popup时在ios端样式错位，故将u-popup的滚动渲染方式改成view overflow。
- 在ios端，当该组件包含在service-pagination中时，显示时需要对service-pagination中的scrollview的样式进行调整，不然会以内嵌的方式显示在页面上
- 修复当mode为center时 点击内容自动关闭的bug 。
### 新增 Props 

参数 |说明|类型|可选值|默认值
---|---|---|---|---
reload|用于需要每次打开都要重新渲染的情况|Boolean|---|false

 



 


 

