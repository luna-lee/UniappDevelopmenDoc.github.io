#  sel-dynamic-table
### 作者：闰月飞鸟；时间：2020/08/29
### 开发目的
- 依据后端配置的动态表单参数，自动生成对应的表格页面

### 设计思路
-  以sel-dynamic-table为基础组件及后端传递过来的表单参数，动态渲染页面

### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
 structureFieldDTOList|表单结构对象数组|Array[Object]|---|必传，格式见下
 structureOption|构造数据属性名配置|Object|---|见下
 entityModelList|实体对象数组|Object|---| --
loading|加载动画|Boolean|--|false
title|表格标题|String|--|""
showType|列表展示形式|String|table、card|"table"
 labelWidth|Form Props label宽度|String, Number|---|40%
 labelStyle|Form Props 若组件单独设置了labelStyle则被覆盖|Object|---|{}
 labelPosition|Form Props label位置,若组件单独设置了,则被覆盖|String|top/left| left
 labelAlign|Form Props label的对齐方式,若组件单独设置了,则被覆盖|String |center / right|left
 errorType|Form Props 错误的提示方式，数组形式,若组件单独设置了,则被覆盖|Array|['message','none','border-bottom','border','toast']|['message']
 disabled|组件是否可用,app,h5端 组件中配置了disabled会覆盖改值|Boolean|--|false
 inputAlign|表单中输入框文字的对齐方式，若组件中自定了inputAlign这覆盖该值，若moon-input中的type为textarea，则设置无效，|String|left，top|left