 #  moon-search

### 作者：闰月飞鸟；时间：2020/07/03
### 开发目的
- 将本项目中多个页面用到的搜索组件及组件样式进行封装
- 统一搜索组件样式。去抖触发搜索。增加下拉选搜索的附加条件。

### 设计思路
-  利用uView的search，button组件 以及moon-pick组件
-  利用去抖函数，触发$emit响应事件
-  由于手机端宽度限制，附加条件一般都为单个，故选moon-pick为单选模式
-  moon-pick 以及button组件的名字，默认展示列表第一个值和label

### Props 
参数 | 说明 |类型|可选值|<div style="width:2rem"></div>默认值
---|---|---|---|---
value/v-model|search内容,|String |——| ""
selector|是否显示按钮|Boolean|true、false|false
show-action|是否显示右侧控件(右侧的"搜索"按钮) ,为true时，input输入后不会自动加载数据|Boolean|true、false|false
action-text|右侧控件文字|String| -|搜索
pickList|moon-pick的list属性 |——|——|——
pickOption|moon-pick的option属性|——|——| {}
inputBgColor|输入框的背景色|String|——| #f2f2f2
bgColor|整个组件的背景色|String|——| white
placeholder|占位符号|String |——| 请输入
hideKeyboard| 输入完成后是否将键盘关闭|Boolean|true、false|false


###  Events
名称 |说明| 参数| 返回类型
---|---|---|---|
search-params|当输入后，获取选择下拉列表改变后，将当前输入的内容与选择的列表value返回|-|Object {inputValue:'',pickValue:""}