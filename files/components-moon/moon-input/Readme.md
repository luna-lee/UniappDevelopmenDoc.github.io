#  moon-input 

### 作者：闰月飞鸟；时间：2020/06/26
### 开发目的
- 使用uView中u-input组件样式重新封装，新增右侧图标props
### 设计思路
- 当输入的内容超过20个字符则以文本框的形式展示

### Props 
参数 | 说明 |类型|可选值|<div style="width:2rem"></div>默认值
---|---|---|---|---
rightIcon| 右侧u-icon图标名称，若有rightIcon属性则显示，否则不显示|String|u-icon所有图标|——
disabled| 为true时，则直接渲染成文本而不用input元素渲染|Boolean|——|false
extraText| 右侧额外的文字说明，若有extraText属性则显示，否则不显示|String|——|——
u-input所有属性| inputAlign：当type为textarea时，始终为left|——|——|——
height|高度，type 为 text 和teatarea的都为70|Number，String|——|70
extraStyle| 右侧额外的文字样式|Object|——|{}
moonStyle | moon组件自定义样式|Object|——|{}
disabledPlaceholder|disabled时占行字符，|String|——|&nbsp;
###  Slot
名称 |说明
---|---
default|  自定义内容
rightIcon |  右侧icon

###  Events
名称 |说明| 参数
---|---|---|
click|u-input点击事件|-

 

