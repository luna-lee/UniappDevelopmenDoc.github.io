# crop-image
###  作者：闰月飞鸟；时间：2020/06/28
###  实现功能
 1. 接收默认图片/选择图片库裁剪。
 2. 可以任意控制裁剪区域大小
 3. 确定后将得到的临时路径地址返回触发页面/组件

 
### 页面Methods 

名称 |说明|参数
---|---|---|
setParams| 设置crop-image的参数 |{ defaultUrl, vm } 

### setParams方法参数

名称 |说明|默认值
---|---|---|
defaultUrl| 图片默认url路径，https路径时会先下载好后再展现 |- 
vm|触发实例上用getWebViewMessage方法接收返回的数据。|null

```
 触发页面开启
async openwebView() {
	let nextPage = await this.$utils.uni.navigateTo('/pages_common/crop-image/crop-image');
	nextPage.$vm.setParams({ defaultUrl: this.imageSrc, vm: this });
},
		
触发页面/组件接收返回数据
methods:{
	onCropConfirm(filePath){
		console.log(filePath)
	}
}

```