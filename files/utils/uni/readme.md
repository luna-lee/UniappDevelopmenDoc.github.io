# uniapp 封装方法
## toast  
- 封装showToast 统一应用showToast风格
- 参数：title标题名
- 返回一个prmoise，toast消失后resolve 

参数|说明|类型|默认值
 ---|---|---|---
 title|显示内容|String|——

``` javascript
await this.$utils.uni.toast.success(title)             
await this.$utils.uni.toast.error(title)
```

## showLoading  
- 封装showLoading mask统一为true，
- 更新storage 用于hideLoading判断当前状态
- 参数：title标题名

参数|说明|类型|默认值
 ---|---|---|---
 title|显示内容|String|——

``` javascript
this.$utils.uni.showLoading(title)             
```

## hideLoading  
- 封装hideLoading  
- 判断当前localstorage中的showLoading状态，若为true 则执行关闭，若为false则不执行

``` javascript
this.$utils.uni.hideLoading()             
```
 ## navigateTo redirectTo reLaunch switchTab

参数|说明|类型|默认值
 ---|---|---|---
 url| 跳转路径|String|——
 params|附带参数，若url中有参数则会自动在原有的参数上追加。若参数名重复，则依据三个参数merge为true时，覆盖追加，false时保留追加|Object|——
 merge|参数的追加方式|Boolean|true

- 封装navigateTo redirectTo reLaunch
- 为避免因拼接参数导致意料之外的错误。switchTab中url因官方要求不能带参数
- navigateTo方式下，返回一个 Promise对象   resolve返回下个页面对象
- 注意：当url中有参数，且与params中的重叠时 ，则依据三个参数merge为true时，覆盖追加，false时保留追加。默认为merge为true，即以params中的参数为准
- 若url为http，则直接用webView跳转

``` javascript
this.$utils.uni.navigateTo("pages/index/index",{a:'a'}) 
this.$utils.uni.navigateTo("pages/index/index?a=c",{a:'a'}) >> a=a
this.$utils.uni.navigateTo("pages/index/index?a=c",{a:'a'},false) >> a=a
this.$utils.uni.redirectTo("pages/index/index",{a:'a'})             
this.$utils.uni.reLaunch("pages/index/index",{a:'a'})   
this.$utils.uni.reLaunch("pages/index/index",{a:'a'})   
this.$utils.uni.switchTab("pages/index/index")   
```


## navigateToWebView
- 打开一个新的webview页面。 
``` javascript
this.$utils.uni.navigateToWebView() 
传递给webview页面的url，title，参考公共页面open-webview页面说明 
```

## setNavigateButton
 - App H5端 动态设置原生导航栏按钮。
 - @param {buttons}  Array[Object] / Object /String,Function( text,onclick)
 - @return {Boolean} true/false
 * 传入的参数是Array[Object]则视为重新构建导航栏按钮数组。传入的button参数参考H5+文档。
 * 传入的参数是Object则视为重新构建导航栏第一个按钮。传入的button参数参考H5+文档。
 * 传入的参数是String ，Function 则视为重新构建导航栏第一个按钮。 String为按钮名称，Function为按钮响应事件
 * 当对象中包含icon属性时，则使用uni官方的字体库/static/fonts/uni.ttf
 * 默认按钮样式为fontSize: '16',fontWeight: "bold",width: "60px";也可以自己设定
``` javascript
this.$utils.uni.setNavigateButton("保存",function(){}) 
this.$utils.uni.setNavigateButton({
	text:"保存",
	onclick:function(){}
}) 
this.$utils.uni.setNavigateButton([{
	text:"分享",
	onclick:function(){}
},
{
	text:"保存",
	onclick:function(){}
}]) 
```

## getPageByRoute
- 通过传入的route得到对应的页面对象，
- 返回一个页面对象

参数|说明|类型|默认值
 ---|---|---|---
 route|页面路由， 若为falsely 返回当前页面实例， 若匹配到则返回匹配到的页面对象。否则返回null,|String|""
 
``` javascript
this.$utils.uni.getPageByRoute() 
this.$utils.uni.getPageByRoute("pages/...") 
```
## getRouteParams
- 通过传入的route得到对应的页面中路由里的参数，
- 返回一个对象

参数|说明|类型|默认值
 ---|---|---|---
 route|页面路由， 若为falsely 返回当前页面实例， 若匹配到则返回匹配到的页面对象。否则返回null,|String|""
 
``` javascript
this.$utils.uni.getRouteParams() 
this.$utils.uni.getRouteParams("pages/...") 
```


## usePageHooks
- 获取指定页面的指定的生命周期函数并将传入的函数追加到对应的生命周期函数中，最后一起运行。

参数|说明|类型|默认值
 ---|---|---|---
 name|具体的生命周期函数名称,onLoad时自动带上当前页面的参数|String|""
 PageVnode|目标页面路由或对象，String视为路由，Object视为页面对象，若为falsely，则为当前页面|String\Object|""
 fun|若传入函数。则在实例上新增对应的生命周期函数的属性或增加运行过程，否则只是单纯的执行对应的生命周期函数|Function| null
``` javascript
this.$utils.uni.usePageHooks('onLoad') 
this.$utils.uni.usePageHooks("onLoad" ,"pages/...") 
this.$utils.uni.usePageHooks("onPullDownRefresh" , null,()=>{console.log("this is js run onPullDownRefresh")}) 
```
 * @description  app打开指定原始id的小程序
 * @author 闰月飞鸟
 * @param {id} 小程序 原始id
 * @param {option} 跳转参数 参考http://www.html5plus.org/doc/zh_cn/share.html#plus.share.WeixinMiniProgramOptions

## jumpToMiniProgram

参数|说明|类型|默认值
 ---|---|---|---
 id| 小程序 原始id|String|""
 option|跳转参数 参考http://www.html5plus.org/doc/zh_cn/share.html#plus.share.WeixinMiniProgramOptions|Object|{}
 
``` javascript
this.$utils.uni.jumpToMiniProgram('xx') 
```


## requestPermissions
- 依据传入的权限名，判断App端的必要权限是否获取成功，若获被永久禁止则需要调出app的权限设置界面。

参数|说明|类型|默认值
 ---|---|---|---
 permissList|权限名列表|Array|[]
 
``` javascript
 //#ifdef APP-VUE
 this.$utils.uni.requestPermissions([
	'READ_CALL_LOG'
 	'CALL_PHONE',
 	'WRITE_CALL_LOG',
 	'RECORD_AUDIO',
 	'CAMERA'
 ]);
 //#endif
```

## getLocation
 * @description 对业务中获取当前地址方法uni.getLocation进行统一默认规范设置，异步操作
 * @return  成功后返回一个文档中成功后的对象,失败返回undefined，并提示错误信息


 参数|说明|类型|默认值
 ---|---|---|---
 option|uni.getLocation所有参数|Object|type为"gcj02"，geocode为true
 
``` javascript
 //#ifdef APP-VUE
 this.$utils.uni.getLocation().then(res=>{});
 let res= await this.$utils.uni.getLocation()
 //#endif
