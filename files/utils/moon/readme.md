 
# 自定义方法
## getVnodeByRef  
- 从指定的vnode中查找ref为name的子孙vnode

参数名|说明|类型|默认值
 ---|---|---|---
 vm|指定开始查找的vnode，可以是当前vnode(this)|VNode|—— 
 name|待查vnode的ref名称|String|——
- 返回： 返回第一个被查到的Node
``` javascript
this.$utils.moon.getVnodeByRef(vm, name)
```

## mergeObj  
- 将两个对象合并，若属性为null则取默认对象值

参数名|说明|类型|默认值
 ---|---|---|---
 defaultObj|默认对象|Object|—— 
 exObj|待合并对象|Object|——
- 返回：合并后的Object
``` javascript
this.$utils.moon.mergeObj({}, {})
```

## getTreeData  
- 将原始树数据格式化成树形数据

参数名|说明|类型|默认值
 ---|---|---|---
 list|原始树数据|Array|——
option|树数据结构的构建字段名称|Object|{}详情见下方

### option参数说明，传入的参数可以随意。在函数内部会将默认值与option对象进展merge
参数名|说明|类型|默认值
 ---|---|---|---
 id|构建树形参数|String|""
 parentId|构建树形参数|String|""
 childrenName|构建树形参数|String|""
 index|为每个节点添加其所在同级节点中的下标|String|""
 rootId|手动指定根节点的ID，若为falsely，则自动推算出根节点  |String|""
 leafChildren|为兼容不同组件需求，添加该属性，当设置为false时，则末节点不会有children属性，否则为空数组.默认true即末节点上也有children属性 |Boolean|true
- 返回： 树形数组
- 更新，每一组的列上都加上对应所在组的下标index，可以指定存储名字。默认index, <font>返回的下标是字符串类型，不是数字类型</font>
``` javascript
this.$utils.moon.getTreeData(list, {
	id :'id',
	parentId : 'parentId',
	childrenName :"children",
	index: "index",
	rootId:"",
	leafChildren:true
})
```



##  isType
-  判断 数据类型。type 为首字母大写的数据类型

参数名|说明|类型|默认值
 ---|---|---|---
 value|--|Object|—— 
 type|--|String|——
- 返回： 函数字符串
``` javascript
this.$utils.moon.isType(obj,'Object')
```

 
##  Object_FunToStr
-  将对象中的函数转成字符串。 
-  为解决 renderjs等逻辑层与应用层 不能传递函数的问题
-  由于小程序限制，该方法不能用

参数名|说明|类型|默认值
 ---|---|---|---
 obj|--|Object/Array|—— 
- 返回： 函数字符串
``` javascript
this.$utils.moon.Object_FunToStr(obj)
```
## Object_StrToFun    
- 将对象中的字符串函数还原成函数
- 返回： 函数

参数名|说明|类型|默认值
 ---|---|---|---
 obj|--|Object/Array|—— 

``` javascript
this.$utils.moon.Object_StrToFun(obj)
``` 


## urlAddQueryParams    
- 在url后面追加指定对象作为新的参数
- 返回：url

参数名|说明|类型|默认值
 ---|---|---|---
 url|需要追加参数的url|String|—— 
 paramsObj|具体的参数对象url|Object|{}
  merge|参数的追加方式,对原有的url参数进行覆盖合并，还是保留合并，true时为覆盖合并，以当前参数为主，false则为保留合并，以原来的url参数为主 。默认为覆盖合并。即有相同参数的以后传的参数值为准|Boolean|true
``` javascript
this.$utils.moon.urlAddQueryParams(url,params)
this.$utils.moon.urlAddQueryParams(url,params,false)
``` 

## getUrlParams    
- 取url中的参数 
- {rootUrl,urlParams} 返回 rootUrl以及urlParams对象

参数名|说明|类型|默认值
 ---|---|---|---
 url|url|String|—— 
 opt| qs.parse第二个参数 |Object|{}
 
``` javascript
let  {rootUrl,urlParams}= this.$utils.moon.getUrlParams(url)
let  {rootUrl,urlParams}=this.$utils.moon.getUrlParams(url,{decode:false})
``` 


## qsStringify    
- { obj} 序列化对象
- {opt}  qs.stringify第二个参数   
- return string 返回 序列化后的字符串 ，默认返回结果带上?

参数名|说明|类型|默认值
 ---|---|---|---
 obj|序列化对象|Object|—— 
 opt| qs.stringify第二个参数 |Object|{}
 
``` javascript
let  str= this.$utils.moon.qsStringify(obj)
let  str=this.$utils.moon.qsStringify(url,{addQueryPrefix: false})
``` 
