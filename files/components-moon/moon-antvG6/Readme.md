#  moon-antvG6

### 作者：闰月飞鸟；时间：2021/04/02
### 开发目的
- 封装echarts组件

### 平台适用性
App, H5|小程序
---|---
√|x


### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
option|echarts属性|——|——|必传
height|高度|——|——|300px
width|宽度|100%


```
return {
			option: {
				linkCenter: true,
				modes: {
					default: ['drag-canvas', 'zoom-canvas']
				},
				defaultNode: {
					type: 'rect',
					size: [40, 40],
					style: defaultNodeStyle,
					labelCfg: defaultLabelCfg
				},
				defaultEdge: {
					type: 'flow-line',
					style: defaultEdgeStyle
				},
				nodeStateStyles: defaultStateStyles,
				edgeStateStyles: defaultStateStyles,
				layout: defaultLayout,
				data: {
					id: 'root',
					label: 'root',
					type: 'circle',
					style: {
						fill: 'red',
						stroke: '#40a9ff',
						radius: 5,
						hover: {
							stroke: 'yellow',
							lineWidth: 11
						}
					},
					children: [
						{
							id: 'c1',
							label: 'c1',
							style: {
								fill: 'red',
								stroke: '#40a9ff',
								radius: 5,
								hover: {
									stroke: 'yellow',
									lineWidth: 11
								}
							},
							children: [
								{
									id: 'c1-1',
									label: 'c1-1'
								},
								{
									id: 'c1-2',
									label: 'c1-2',
									children: [
										{
											id: 'c1-2-1',
											label: 'c1-2-1'
										},
										{
											id: 'c1-2-2',
											label: 'c1-2-2'
										}
									]
								}
							]
						},
						{
							id: 'c2',
							label: 'c2'
						},
						{
							id: 'c3',
							label: 'c3',
							children: [
								{
									id: 'c3-1',
									label: 'c3-1'
								},
								{
									id: 'c3-2',
									label: 'c3-2',
									children: [
										{
											id: 'c3-2-1',
											label: 'c3-2-1'
										},
										{
											id: 'c3-2-2',
											label: 'c3-2-2'
										},
										{
											id: 'c3-2-3',
											label: 'c3-2-3'
										}
									]
								},
								{
									id: 'c3-3',
									label: 'c3-3'
								}
							]
						}
					]
				},
				renderFun: () => {
					G6.registerEdge('flow-line', {
						draw(cfg, group) {
							const startPoint = cfg.startPoint;
							const endPoint = cfg.endPoint;
							const { style } = cfg;
							const shape = group.addShape('path', {
								attrs: {
									stroke: style.stroke,
									endArrow: style.endArrow,
									path: [
										['M', startPoint.x, startPoint.y],
										['L', (startPoint.x + endPoint.x) / 2, startPoint.y],
										['L', (startPoint.x + endPoint.x) / 2, endPoint.y],
										['L', endPoint.x, endPoint.y]
									]
								}
							});
							return shape;
						}
					});
				}
			}


```
 

