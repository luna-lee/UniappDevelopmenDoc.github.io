 #  moon-picker

### 作者：闰月飞鸟；时间：2020/06/27
### 开发目的
- 实现有默认值或者选中后，再次打开面板直接定位到当前选中项
- 多级联动 实现将扁平树结构数据格式化成组件需要的树数据。
- 统一数据获取方式/返回格式, v-model传入/接收值。 selected 返回选中的数据所对应list中的项

### 设计思路
- v-model 用于接收所选择的数据/设置默认值。
- 利用一个简单的算法，得到满足u-select中default-value的类型值，同时将对应list中的项通过事件返回
- u-select的开启，父组件通过ref调用open方法

### 注意
-  当多级/多级联动时，list的每条数据的深度必须一致。

### 更新 作者：闰月飞鸟；时间：2020/08/18
- 重新实现面板默认值的赋值过程。
- 当传入的value为对应list中的label项时。也能匹配出响应的数据。并且将源数据改成对应的value数据。
- 如性别字典。当不知道字典值时，可以直接传入中文，组件会自动将对应的value值返回并重新写入


### Props 
参数 | 说明 |类型|可选值|<div style="width:2rem"></div>默认值
---|---|---|---|---
value/v-model|接收所选中的值/默认值，(值为对应list中的指定的inner_option中的value属性名的值)|String|——|——
list|数据列表 |Array|——|——
mode|u-select中的mode |——|——|——
option|数据属性名，具体参数见下放说明|Object|——| {}
disabled|组件是否可用|Boolean|--|false
show.sync|面板开启关闭|Boolean|--|false

#### option

参数 | 说明 |类型|可选值|<div style="width:2rem"></div>默认值
---|---|---|---|---
label|指定展示值对应list项的属性名,并将其设置为u-select中label-name值|String|——|label
value|指定返回值对应list项的属性名,并将其设置为u-select中value-name值 |String|——|value
id|作用:多级联动，将扁平树数据构造树形数据，必须的参数 |String|——|id
children|作用:多级联动，将扁平树数据构造树形数据，必须的参数。并将其设置为u-select中child-name值|String|——| children
parentId|作用:多级联动，将扁平树数据构造树形数据，必须的参数|String|——| parentId
format|多级联动，是否需要将传入的数据格式化成树形数据 |Boolean|——| true



###  Events
名称 |说明| 参数| 返回类型
---|---|---|---|
selected|传入默认值/选中确定后返回，对应list中的项|-|Array
 