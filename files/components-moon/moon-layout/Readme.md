#  moon-layout

### 作者：闰月飞鸟；时间：2020/03/14
### 开发目的
- 页面顶部/页面底部固定布局。用于渲染tabs与底部button
### 设计思路
- 高度依赖于父组件外框的高度。不用view包裹则取page高度 
- 为进一步统一项目样式，当开启底部默认slot->按钮 ,顶部默认slot->选项卡时，自动渲染出对应的组件。
- 由原来的flex布局，改用absolute布局 ,因为flex布局后无法嵌套
- 使用组件时，外层有嵌套moon-layout则必须指定height高度。可以是100%;

``` 
	<moon-layout>
		<view slot="bottom" style="display:flex;flex-direction: row;justify-content: center; align-items: center; height: 100%;">
					<button size="default" >提交</button>
		</view>
	</moon-layout>
```
### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
heightTop|顶部高度|Number|—|100
heightBottom|底部高度|Number|—|110
bottonButton|开启底部默认slot->按钮|Boolean|—| false
buttonOption|按钮属性对象|Object|—| {text: '提交', type: 'primary'}
topTabs|开启顶部默认slot->选项卡|Boolean|—|false
tabCurrent.sync|当前活动状态的tab下标|Number|—|0
tabList|tabs数据源|Array|—|[]
tabProps|uView中的其他props|Object|—|{isScroll:false, barWidth:100, duration:0.1, fontSize:30, 	height:80, activeColor:'#2979ff'}
	 
###  Slot
名称 |说明
---|---
default |中间默认视图
top|顶部视图
bottom|底部视图
tab[0~tabList.length-1]|当配置tabList时 ，增加对应每个tab页签的slot插槽。名称为tab+对应的下标。第一次加载时，未点击的页面都不会渲染，返回查看时缓存视图
 
 ###  Events
名称 |说明| 参数
---|---|---|
bottomButtonClick|底部按钮点击事件|-
tabsChange|顶部选项卡改变事件|index，当前点击的选项卡下标


 ###  Method
名称 |说明| 参数
---|---|---|
refreshLayout|重新渲染布局,需要配合$nextTick。| 
 

