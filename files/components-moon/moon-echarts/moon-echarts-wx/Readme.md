# moon-echarts-wx

### 作者：闰月飞鸟；时间：2021/04/02
### 开发目的
- 封装echarts组件
- 小程序端的宽高，可以在使用时通过style直接指定
- 示例中static中的echarts是在4.0版本的基础上自定义的， 只包含 图表：柱状图  折线图 饼图 组件：直角坐标系 工具： Title 提示框 数据区域缩放  
- 由于echarts文件比较大。开发小程序时最好将次文件放入分包文件夹中，作为分包组件调用。

- [参考](https://github.com/ecomfe/echarts-for-weixin/tree/master/ec-canvas)

### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
option | echarts属性  

``` js

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