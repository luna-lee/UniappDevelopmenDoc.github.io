
#  service-select-city
### 作者：哇凉哇凉；时间：2020/09/08
### 开发目的
- 封装并优化uview城市选择模板，返回项目字典中所选对应的最后一个地区的id。
### 设计思路
- 依据value查出字典中所对应的区域文字。由于value存的是地区层级树最后一个id，故需要遍历出其父级区域
- 找到字典中对应所选文本的id，从右往左遍历匹配。匹配到即返回。

### Props 

参数 |说明|类型|可选值|默认值
---|---|---|---|---
value/v-model|  value存的是地区层级树最后一个id， |String|——|""
value4.sync|接收返回label|String|——|——
rightIcon|右侧图标|String|uview图标| arrow-right
inputAlign|内容显示的位置|String|left center right| left
placeholder|占位|String|——|请选择
disabled|禁用|Boolean|——|false
level|展示层级，默认0 展示所有|Number|——|0 