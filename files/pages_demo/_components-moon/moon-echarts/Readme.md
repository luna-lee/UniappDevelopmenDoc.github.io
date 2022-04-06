# moon-echarts

### 作者：闰月飞鸟；时间：2021/04/02
### 开发目的
- 封装echarts组件
- 微信端必须在自定组件名上添加宽高
- 由于echarts文件比较大。开发小程序时最好将次文件放入分包文件夹中调用。

### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
option |echarts配置文件|---|---|echarts属性
height|高度，app有效，微信端直接在自定组件名上添加样式|---|---|300px
width|宽度，app有效，微信端直接在自定组件名上添加样式|---|---|100%
 
###  Events
名称 |说明
---|--- 
touchStart|小程序cavans事件 
touchMove|小程序cavans事件  
touchend|小程序cavans事件  

```

{
				tooltip: {
					trigger: 'axis',
					axisPointer: {
						type: 'shadow'
					}
				},
				legend: {
					data: ['人口采集数', '信息核查数']
				},

				xAxis: [
					{
						type: '',
						axisTick: { show: false },
						data: ['2012', '2013', '2014', '2015', '2016']
					}
				],
				yAxis: [
					{
						type: 'value'
					}
				],
				series: [
					{
						name: '人口采集数',
						type: 'bar',
						barGap: 0,
						emphasis: {
							focus: 'series'
						},
						data: [320, 332, 301, 334, 390]
					},
					{
						name: '信息核查数',
						type: 'bar',
						emphasis: {
							focus: 'series'
						},
						data: [220, 182, 191, 234, 290]
					}
				]
			}
```