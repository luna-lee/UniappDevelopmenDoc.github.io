#  moon-tree
 
### 作者：闰月飞鸟；时间：2020/05/21
### 开发目的
-  造树组件轮子，
### 设计思路
-  递归组件， 

```javascript
	 <moon-tree :treeStructure="treeStructure" :treeData="treeData" :multiple="multiple" :accordion="accordion" @selected="onTreeSelect"></moon-tree>
	 小程序上使用，必须在pages.json里 添加
	 "usingComponents": {
	 			"build": "/components-moon/moon-tree/build"
	 		}
```
### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
treeData|扁平化的树数据，数据对象中若包含selected，则默认为选中状态，且展开所有祖先节点|Array|—|【】
treeDataBackUp|用于在搜索模式下存储数据源，用在多选模式下遍历出当前所有所选的数据。若不传则默认使用treeData|Array|—|【】
treeStructure|将扁平树数据构造成树的参数|Object|—|{ id: 'id', parentId: 'parentId', label: 'value' }
leftIcon|展开折叠图标，默认使用u-icons图标库，若用其他的，可以修改treeicon组件即可。|Array|—| ['arrow-right', 'arrow-down']
multiple|多选单选标记，false：单选，true：多选|Boolean|true/false| false
accordion|手风琴效果|Boolean|true/false| false;
hidden|隐藏选择装态，则不会出现checkbox 和radiobutton   每次点击末节点都会弹出对应所选的对象，|Boolean|true/false| false;	
canSelectParentNode|父节点可以点击，为true时 只能点击展开图标展开子节点|Boolean|true/false| false;
###  Events
名称 |说明
---|---
selected |返回当前选中的对象数组。单选时返回当前数据源长度，用于判断是否需要更新数据
click|当hidden时 返回所点击的末节点对象。

 
 


 

