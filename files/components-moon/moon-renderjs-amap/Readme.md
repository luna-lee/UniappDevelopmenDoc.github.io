#  moon-renderjs-amap

### 作者：闰月飞鸟；时间：2021/06/09
### 开发目的
- 封装高德地图组件

### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
option |高德属性配置,默认配置zoom: 14, zooms: [3, 20], expandZoomRange: true, 	resizeEnable: true|-|-|-

###  Events
名称 |说明| 参数
---|---|---|
markclick|marked点击事件,返回对应的数据对象|-
infoWindowClick|infoWindow点击事件,返回对应的数据对象|-
 ```
 option={
	 showType:'Markers',  展示模式， Markers 少量点标记和路径区域覆盖物。  LayerMarkers 设置标注和标注图层 海量点   默认为Markers
	 	mapOptions: {
	 		zoom: 15,
	 		center: [120.10775, 30.264786],
	 		resizeEnable: true,
	 	},
		polygonPathAsyncData:[],<!-- 异步添加 -->
	 	polygonPath: [
	 		{
	 			// 右下
	 			latitude: 30.264786,
	 			longitude: 120.10775
	 		},
	 		{
	 			// 右上
	 			latitude: 30.268786,
	 			longitude: 120.10775
	 		},
	 		{
	 			// 左上
	 			latitude: 30.268786,
	 			longitude: 120.10575
	 		},
	 		{
	 			// 左下
	 			latitude: 30.264786,
	 			longitude: 120.10575
	 		},
	 		{
	 			// 左下
	 			latitude: 30.264786,
	 			longitude: 120.10775
	 		}
	 	],
	 	marker: {
			asyncData:[],<!-- 异步添加 -->
	 		position: [
	 			{
	 				id: '0',
	 				latitude: 30.264786,
	 				longitude: 120.10775,
					//若InfoWindow为truely 则点击后弹出
	 				InfoWindow: `<div class="test">dddd  
	 				</div>`,
					markIcon:"..."
	 			},
	 			{
	 				id: '1',
	 				latitude: 30.268786,
	 				longitude: 120.10775,
	 				InfoWindow: 'this is 1'
					markIcon:"..."
	 			},
	 			{
	 				id: '2',
	 				latitude: 30.268786,
	 				longitude: 120.10575,
	 				InfoWindow: 'this is 2'
					markIcon:"..."
	 			},
	 			{
	 				id: '3',
	 				latitude: 30.264786,
	 				longitude: 120.10575,
	 				InfoWindow: 'this is 3'
					markIcon:"..."
	 			}
	 		]
	 	}
	 
 }
 
 ```


 

