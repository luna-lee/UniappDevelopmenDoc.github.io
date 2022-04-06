# rich-editor
###  作者：闰月飞鸟；时间：2020/09/28
###  实现功能
 1. 富文本编辑
 2. 图片直接提交到文件服务器
 
### 实现方式
-  封装uniapp官方提供的editor组件。
-  以页面的形式操作数据。
-  可以接收/返回传入的html数据。
-  当富文本修改后未保持，触发返回按钮时提示保存
### 页面Methods 

名称 |说明|参数
---|---|---|
setParams| 传入触发页面的Vue实例，和默认富文内容  |vm,content


### setParams方法参数
名称 |说明|默认值
---|---|---|
vm|传入触发页面的vue实例，<font color='red'>触发页面需要实现onRichEditorConfirm方法，用于接收返回的富文本html数据</font>|null
content|默认富文内容|''

```
 触发页面开启
async editorView() {
	let page = await this.$utils.uni.navigateTo('/pages_common/rich-editor/rich-editor') 
	page.$vm.setParams(this,'');
},
		
触发页面/组件接收返回数据
methods:{
	onRichEditorConfirm(html){
		console.log(html)
	}
}



外部页面
 用this.$route.query接收  parsms参数值
 通过当前父WebviewObject实例中的getStyle方法获取postData值(即options中的data值)
 let data = plus.webview.currentWebview().parent().getStyle().postData;

通过uni-weiview中的方法，将页面操作的数据进行返回。


```
 