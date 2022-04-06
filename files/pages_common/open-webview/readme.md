# open-webview
###  作者：闰月飞鸟；时间：2020/06/28
###  实现功能
 1. 使用web-view跳转到外部网页
 
 
### 实现方式
- 将web-view组件封装到一个新页面中
- 注意不能将web-view直接以组件的形式调用，weib-view会覆盖原来的页面。

### 页面Methods 
名称 |说明|参数
---|---|---|
setParams| 设置webview必要的参数,<font color='red'>组件中会自动带上当前token与接口的域名地址，不需要额外添加</font>  |--

### setParams方法参数
名称 |说明|默认值
---|---|---|
url|web-view跳转地址，hash模式一定要有‘/#/’ |- 
params| 跳转时，url上带的参数，页面title只从params中获取  。params只用于传递字符串|{}
postData| 跳转时，绑定在webviewObject对象上的style对象中的数据，网页中通过找到父webviewObject来接收其值。可以传递对象，数组 |{}
vm|触发开发webview的vue实例，<font color='red'>若需要接受webview页面的返回值则该实例上需要实现getWebViewMessage方法，用于接收网页返回的数据。同时当webview触发返回时，会执行该实例上的onWebViewBack方法(若有)，</font>|null

```
 触发页面开启
async openwebView() {
	let webViewPage = await this.$utils.uni.navigateToWebView() 
	或
	let webViewPage = await this.$utils.uni.navigateTo('/pages_common/open-webview/open-webview') 
	webViewPage.$vm.setParams({ url:'http://www.baidu.com',  parsms:{title:'WEB页面',...rests},postData:{},vm:this});
},
		
触发页面/组件接收返回数据
methods:{
	getWebViewMessage(data){
		console.log(data)
	}
}



外部页面
 用this.$route.query接收  parsms参数值
 通过当前父WebviewObject实例中的getStyle方法获取postData值(即options中的data值)
 let data = plus.webview.currentWebview().parent().getStyle().postData;

通过uni-weiview中的方法，将页面操作的数据进行返回。


```
 