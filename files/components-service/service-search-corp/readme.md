#   service-search-corp

### 作者：闰月飞鸟；时间：2020/05/21
### 开发目的
- 依据企业id展示企业名称，点击后可以从企业库里返回企业id。

### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
value/v-model|接收返回企业ID|String|—| ""
inputAlign|内容的展示方式|String|left center right| left
show-action|是否显示右侧控件(右侧的"搜索"按钮) ,为true时，input输入后不会自动加载数据|Boolean|true、false|true
disabled|禁用|Boolean|——|false

 

###  Slot
名称 |说明
---|---
default|自定义触发以及显示dom，默认是moon-input,  传递一个item参数，为当前所选择的企业对象
 
  ### Events 
名称 |说明 
---|--- 
select|所选企业对象

 
 ``` html
 <service-search-corp v-model="corpId">
 <!-- 自定义 显示-->
 <!-- <view slot-scope="{item}"><u-button> {{item.name}}</u-button></view> -->
 </service-search-corp>
 ```
 