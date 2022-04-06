#  service-image-video
### 作者：闰月飞鸟；时间：2020/03/21
### 开发目的
- 依据文件id，封装图片/视频的获取、展示和上传，并将上传结果返回
### 设计思路
- 多个文件，id中用逗号隔开。
- 为避免因新增删除后返回新的id,内部新定义一个inner_value来接收上传后的id，同时watch传入的value 只有当value值与inner_value值不想同时才初始化

### 更新 作者：闰月飞鸟；时间：2020/08/03 
- 更新内容，内部提交逻辑重新实现，
- props中添加width，height用于用户指定图片的宽度高度
- 修改默认添加按钮样式，同时支持slot自定义添加按钮。

### 更新 作者：闰月飞鸟；时间：2020/08/017 
- 更新内容，实现文件预览，如word，execl等，

### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
type|媒体文件/所有文件|String|medium,file,image,video|medium
value|文件ID，多个文件逗号开，若包含https/http，或本地文件路径,则直接显示，且上传时只能手动上传|String|--
mode|图片模式|String|参考官方文档image组件|aspectFit
disabled|是否只读，true时不能做添加删除操作|Boolean|——|false
count|选择最大个数限制|Number|——|9
width|图片宽度以及添加组件外围宽度，upx|String，Number|200
height|图片高度以及添加组件外围高度，upx|String，Number|200
autoUpload|是否自动上传|Boolean|——|true
defaultImage|图片加载出错/返回数据格式不对时，显示默认的图片|String|——|""
borderRadius|圆角值，单位任意，如果为数值，则为rpx单位|String，Number|0
shape|图片形状，circle-圆形，square-方形|String|circle|square
### Slots
名称 |说明 
---|--- 
addBtn| 自定义的选择图片按钮 
fileTag|当文件不是图片时，以何种形式表现。默认展示当前文件名
### Methods
名称 |说明 
---|--- 
upload|  autoUpload为false时，为手动上传，通过ref调用该方法上传数据。

 


 

#  compressH5 JS
### 作者： 闰月飞鸟；时间：2020/09/24
### 开发目的 
- H5图片压缩，同时解决不同手机拍照图片旋转问题
- [参考文献](https://ext.dcloud.net.cn/plugin?id=2816)
- [参考文献](https://blog.csdn.net/xiaoermingn/article/details/94398621)
```
	import { compressH5Init } from '../compressH5/compressH5.js';
	maxW   1024;  压缩时最大宽度
	maxH  1024;	压缩时最大高度
	quality  0.8; 质量
	base64  false; 是否返回base64
	await compressH5Init(files, { base64: true });
	
```

# 第三方库 izExif.js
### 作者： 134***@qq.com    1.0.0（2021-02-14
### 开发目的 
- 通过一个函数就可以方便的获取图片的exif和iptc信息包含gps地理位置等
- [使用说明](https://ext.dcloud.net.cn/plugin?id=4183)
- [修复bug时参考文献](https://blog.csdn.net/qq_22266149/article/details/101285632)
- [参考文献](https://www.cnblogs.com/Bideam/p/5799751.html)

 