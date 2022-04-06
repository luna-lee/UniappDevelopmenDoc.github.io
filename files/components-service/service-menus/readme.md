# service-menus
### 作者：闰月飞鸟；时间：2020/04/28
### 开发目的
- 封装渲染页面菜单。
### 设计思路
-  登录成功后将菜单列表以页面路由为对象属性，子页面为值的形式存入store中，每个打开页面只需依据当前页面路由到store中提取相应的页面菜单列表即可。 
-  每个菜单上的角标数值，依据菜单对应的路由从store里取，若没有则不显示
-  菜单显示模式:会依据 config中不同运行环境配置的menuType来获取。 localMenuTree 显示全部本地菜单 通过access控制权限，serviceMenuTree 显示服务端菜单


### Props 

参数 |说明|类型|可选值|默认值
---|---|---|---|---
defaultIcon|默认图标路径，当没有串icon或加载失败则使用默认图标路径|String|——|""
layout|菜单展示方式，侧滑滚动，卡片|String|card/list|"card"
autoRoute|true 点击图标自动跳转，， false时则触发事件itemClick，将当前点击的项返回|Boolean|——| true
rowNumber|每行显示的个数|Number|——| 4
menus|页面菜单,优先从组件外部获取，若没有则以当前页面路由为属性去store中查找|Array|——|[]
cardList|页面层级菜单，优先从组件外部获取，若没有则以当前页面路由为属性去store中查找|Array|——| []
 menusCardBodyStyle|页面菜单，卡片内容样式|Object|——| {padding: '30px 15px 15px 15px'}
 cardListHeadStyle|页面层级菜单，卡片头样式|Object|——|{fontWeight: 'bold', padding: '20upx 0 0 20upx'}
 cardListBodyStyle|页面层级菜单，卡片内容样式|Object|——| 	{padding: '15px 0 0 0'}
 gridBgColor|网格背景|String|——|white
 gridItemBgColor|网格item背景|String|——|transparent
 gridItemContentStyle|网格item内容样式|Object|——|{height: '200rpx'}
 textStyle|网格item内容文字样式|Object|——|{ }
 imageWidth|网格item内容图片宽度|String, Number|——|80
 imageHeight|网格item内容图片高度|String, Number|——|80
 badgeOffset| 设置badge的位置偏移，格式为 [x, y]，也即设置的为top和right的值，单位rpx。 |Array|——|[-10, -10]

 
 
 
 ### Events 
名称 |说明 
---|--- 
itemClick|当autoRoute为false时触发，返回当前所点击的对象, 当autoRoute为true时。若url为全路径即有https/http，则直接通过webview打开，若url为“@前端参数名@/具体的路径”则会用前端参数对象中对应的属性值替换。否则直接跳转，默认跳转方式是navigateTo，同时若设置了跳转方式则使用所设定的跳转方式

###  Slot
名称 |说明
---|---
right | list模式下 u-cell-item 中的right-icon slot
img|图标
 
 
``` javascript
menus模板：
[
		{
				"name": "企业列表",
				"url": "/pages/modules/baseData/enterprise/list",
				"icon": "corp.png",
				"navigate":"navigateTo"//跳转方式
				"access": true
			},
			{
				"name": "人房采集",
				"url": "/pages/modules/baseData/housePeople/community/list",
				"icon": "house.png",
				"navigate":"switchTab"
				"access": true
			}
]

cardList模板：[{
			"name": "事件报送",
			"url": "",
			"icon": "",
			"children": [{
					"name": "自报自结",
					"url": "/pages/about/myEvent/event/bussinessView/view/main",
					"icon": "/static/img/event/self.png",
					"access": true
				},
				{
					"name": "上报处理",
					"url": "/pages/about/myEvent/event/bussinessView/view/main",
					"icon": "/static/img/event/report.png",
					"access": true
				},
				{
					"name": "领导交办",
					"url": "/pages/about/myEvent/event/bussinessView/view/main",
					"icon": "/static/img/event/leader.png",
					"access": true
				}
			]
		}]
```
 
 

