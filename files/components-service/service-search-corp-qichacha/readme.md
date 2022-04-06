#   service-search-corp-qichacha

### 作者：闰月飞鸟；时间：2020/09/16
### 开发目的
- 输入企业名称自动搜索企业库与企查查。返回所选择的数据对象，

### Props 

参数 |说明|类型|可选值|默认值
---|---|---|---|---
value/v-model| model值为inputView时 接收返回企业名称，popupView时接受返回的是企业Id|String|—| ""
mode| 直接input输入下拉显示，or 侧边弹出popup框显示|String|—| "popupView"
inputAlign|内容的展示方式|String|left center right| left
len| model值为inputView时 搜索条件文字长度，默认是在两个字符长度的时候开始搜索|Number|——|2
disabled|禁用|Boolean|——|false 
- 注意：当value值发生改变后，会直接触发slect事件，抛出一个空对象。父组件清空绑定的数据。当重新选择一个后则会重新发select并抛出当前所选对象
 

### Events 
名称 |说明 
---|--- 
select|所选企业对象

 
 ``` html
 < service-search-corp-qichacha v-model="corpName">
 <!-- 自定义 显示-->
 <!-- <view slot-scope="{item}"><u-button> {{item.name}}</u-button></view> -->
 </ service-search-corp-qichacha-search-corp>
 ```
 