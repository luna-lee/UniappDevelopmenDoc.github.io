#  sel-dynamic-query
### 作者：闰月飞鸟；时间：2020/08/22
### 修改升级，2021/08/11
### 开发目的
- 依据查询数据配置，动态生成查询视图， 

### 设计思路
-  只做构造器，不与后台交互
-  查询视图分3个模块，输入模糊查询，下拉列表选择查询，以及更多条件查询。
-  当没有有下拉列表查询时，更多视图应与输入框一排。否则与下拉列表查询一排。
-  使用现有组件，moon-search，service-picker sel-dynamic-form
-  构造数据与表单的构造数据一致。输入查询：取数据中一个组件为moon-input的数据。 下拉列表选择查询：取数据中2-3个组件为service-select、service-select-tree的组件。余下的都为更多视图

### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
queryStructureFieldDTOList|构造数据属性名配置,与动态表单的构造器一直，增加了queryTopStyleWidth属性，用于动态设置下拉选择控件的宽度|Object|---|见下
entityModel.sync|实体对象,若传入象会自动与queryStructureFieldDTOList构建实体对象merge。保留entitModel中的默认值。|Object|---| --
moonSearchInputBgColor|输入框的背景色|String|——| #f2f2f2
moonSearchBgColor|整个组件的背景色|String|——| white
popupHeight|更多面板高度,使用百分比，这样兼容不同大小屏幕|String|——| 50%
defaultTopSelectNum	|顶部默认3个查询条件|Number|——| 3
TopSelectComponentNameList|顶部选择筛选，所展示的组件名|Array|——| ['service-picker', 'service-select-tree']


### Events
名称 |说明
---|---
update:height|组件高度，配合moon-layout 动态设置top页头高度

 

  

### queryStructureFieldDTOList 格式
``` javascript
  
  		{
  			entityFieldName: 'name',
  			label: '企业名称',
  			componentName: 'moon-input',
  			componentOption: {
  				placeholder: '请输入企业名称'
  			}
  		},
  		{
  			entityFieldName: 'regTypeCode1',
  			label: '排序	',
  			componentName: 'service-picker',
			queryStyleWidth:'50%',
  			componentOption: {
  				tagIsRadio: true,
  				outsideList: [
  					{
  						id: '1',
  						value: '增📖'
  					},
  					{
  						id: '0',
  						value: '减🐰'
  					}
  				]
  			}
  		},
 	 {
  			entityFieldName: 'industryCode1',
  			label: '行业',
  			componentName: 'service-picker',
  			componentOption: {
  				code: '2001',
  				cascadeLevel: '1'
  			}
  		},
  		{
  			entityFieldName: 'regTypeCode',
  			label: '类型	',
  			componentName: 'service-picker',
  			componentOption: {
  				code: '2000',
  				cascadeLevel: '1'
  			}
  		},
  				{
  			entityFieldName: 'industryCode',
  			label: '行业',
  			componentName: 'service-picker',
  			componentOption: {
  				code: '2001',
  				cascadeLevel: '1'
  			}
  		},
  		
  		{
  			entityFieldName: 'businessScope',
  			label: '经营范围',
  			componentName: 'moon-input'
  		},
  		{
  			entityFieldName: 'turnover',
  			label: '经营收入',
  			componentName: 'moon-double-input'
  		},
  	{
  			entityFieldName: 'corpTagCode',
  			label: '企业标签',
  			componentName: 'service-tag',
  			componentOption: {
  				code: 3023,
  				cascadeLevel: 2,
  				multiple: true
  			}
  		},
  		{
  			entityFieldName: 'visitUserName',
  			label: '走访人',
  			componentName: 'moon-input'
  		},
  		{
  			entityFieldName: 'startDate',
  			value1: 'endDate',
  			label: '走访日期',
  			componentName: 'moon-datetime',
  			componentOption: {
  				range: true,
  				moonStyle: {
  					border: '1px solid rgba(204, 204, 204, 1)',
  					padding: '0 20rpx'
  				}
  			}
  		},
  		{
  			entityFieldName: 'divisionCode',
  			label: '区域',
  			componentName: 'service-tag',
  			componentOption: {
  				cascadeLevel: '1',
  				code: '0001'
  			}
  		}  
```


 
 



 


 

