#  service-tag
### 作者：闰月飞鸟；时间：2020/07/22

### 开发目的
-  用tag标签形式展示字典内容，以及返回所选标签对应的字典值
-  实现单选，多选，取消所选tag
-  只适合展示小数据量，大数据的展示还是用service-pick
### 设计思路
-  依据code获取字典，遍历渲染tag。
-  点击选中，再点击则取消选中 
-  提供单选多选模式。单选直接返回所选value以及label，多选则返回逗号隔开的字符串


### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
value/v-model| 绑定值，联动选择->type==string为逗号拼接的字符串，type==array为第一列的value|String|——|""
code|字典值，必填|String|——|——
cascadeLevel|字典参数|String|——|——
pCode|字典参数|String|——|——
option|指定返回数据在对象中的属性名|Object|--|{value: 'id', label: 'value' ,disabled:'disabled' }
disabled|禁用|Boolean|--|false
multiple| 选择模式，单选false，多选true |Boolean| --|false
filterValue|过滤选项所对应的value值|Array|——|[]
outsideList|外部传入数据源，若code为falsely则使用该数据源|Array|——|[]
shape|uTag的shape|String|——|circle
type|uTag的type属性|String|——|primary
modeList|uTag 选中和非选中时的mode，下标为0是选中mode，1为非选中|Array|——|[‘dark’，‘plain’]

 ### Events 
名称 |说明 
---|--- 
update:text|返回所选tag对应字典的label值，多选返回逗号隔开的字符串 

