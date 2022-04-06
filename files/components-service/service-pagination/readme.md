# service-pagination
### 作者：闰月飞鸟；时间：2020/06/18
### 开发目的
- 将分页列表中的数据获取，下拉刷新 ，上拉加载，触底加载样式做统一封装。列表的样式在具体业务页面中设计。
### 设计思路
- 组件内获取列表数据，并将列表数据通过slot作用域反馈给父组件。父组件设计具体的列表样式
- 通过scroll-view组件实现下拉刷新 ，上拉加载 


### Provide 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
servicePagination | 存入当前vue实例，子组件通过inject接收，可以用来调用其方法|Vue|——|{}
 


### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
params | 接口参数，除分页参数之外其他请求参数,当参数发生改变时会重新获取数据|Object|——|{}
~~interface~~  interfaceFun| 设置请求接口函数，promis类型,~~<font color='red'>小程序不支持改属性</font>~~, 需要传递一个对象函数的引用。| Object|——|{fun: null}
paginateProp | 分页参数名 |Object|——|{ page: 'page', limit: 'limit' }
responseType | 数据返回格式,项目里要统一 |Object|——| { list: 'page.list' }
limit | 每页数量 |Number|——|20
pullDownRefresh | 开启下拉刷新 |Boolean|——|false
loadmoreBg| loadmore背景色 |String|——|#ffffff
loadText| 加载状态文字 |Object|——|	{ nomore: '没有更多了', loadmore: '上拉加载更多', loading: '正在加载'}

###  Methods
名称 |说明| 参数
---|---|---|
init|依据当前条件，重新获取数据。 | ——
~~setInterface~~|~~由于小程序不支持props传函数，设置请求接口函数，promis类型 ~~|Function

###  Slots
名称 |说明| 参数
---|---|---|
default|作用域slot,prop为listData,loading<font color='red'>当在插槽内容上绑定事件时，小程序上不起作用</font>,若组件中需要执行页面中的方法，可以通过this.$utils.uni.getPageByRoute 获取到当前页面对象，然后执行具体方法。也可以通过provide将当前对象传递即可| ——


### Event
名称 |说明| 参数
---|---|---|
update:result|接口返回数据| ——
update:listData|当前页面所有列表数据| ——
~~mounted~~|~~组件挂载完后触发事件响应，可以用于传入setInterface，从而避免因为组件没有渲染而赋值失败~~| ——

```
当于moon-layout联合使用时，若在serviec-pagination外层包裹了view 则必须指定view的height:100%
<service-pagination ref="servicePagination" pullDownRefresh :params="queryParams">
			<view slot-scope="{ listData }"><item v-for="(value, index) in listData" :key="index" :item="value"></item></view>
</service-pagination>

	onReady() {
		this.$refs.servicePagination.setInterface(this.$service.enterprise.getList);
	},

```
 

 


 

