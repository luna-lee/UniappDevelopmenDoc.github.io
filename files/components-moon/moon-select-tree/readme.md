#  moon-select-tree

### 作者：闰月飞鸟；时间：2020/05/21
### 开发目的
-   封装moon-tree，用于树选中后数据的展示与修改，
### 设计思路
-   多种触发方式， ，label，tag 
-   label，单行展示，溢出则滚动浏览。tag，标签展示。flex浮动布局。可以直接在标签上点击删除。
-   点击后跳转新的页面，利用组件与页面的数据交互，实现数据存储
-   通过双向绑定，接收和回写数据。多个数据用逗号分隔。

### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
value/v-model|接收和回写|String|-| -
mode|触发组件名|String|label/tag| “tag”
~~showType~~|展示形式|String|webview/component webview只能再App H5端运行，component全端运行 | “component”
moon-tree所有属性|-|-|—|-
treeStructure|将扁平树数据构造成树的参数,<font color="red">其中value为指定返回树数据对象的属性名</font>|Object|—|{ id: 'id', parentId: 'parentId', label: 'value' ,value:"id"}  
title|popup面板标题|String|—| "请选择"
disabled|组件是否可用|Boolean|true/false| false
inputAlign|mode为label时，内容的展示方式|String|left center right| left
rightIcon |input右侧图标|String| --|arrow-right  
filterValue|筛选出指定id的项及子项|String|——|——
filterExceptValue|排除指定id项及子项，多个用逗号隔开|String|——|——
canSelectParentNode|父节点可以点击，为true时 只能点击展开图标展开子节点|Boolean|true/false| false;

###  Slot
名称 |说明
---|---
add-icon |自定义新增图标
