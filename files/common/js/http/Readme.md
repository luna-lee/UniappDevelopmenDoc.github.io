# 依据http接口，配置项目http请求
- baseUrl 全局配置$config中的baseUrl
- 请求拦截中，将token存入header中。并将参数中每个属性值的收尾空格去掉。
- 响应拦截中，依据请求的stateCode值返回处理信息，并直接返回服务器返回的数据response.data。若是第三方接口地址，则直接返回请求后的数据。
- 在请求体中设置 options中的custom对象中的toast属性（get 与其他请求方式传递options的方式不一样,）来控制控制当请求错误是否以toast的形式展示 
 
```
http.get('/corp/base/list', {
		params,
		custom:{
			toast:false
		}
	})
	
http.post('/corp/base/list', params,{
		custom:{
			toast:false
		}
	})
```