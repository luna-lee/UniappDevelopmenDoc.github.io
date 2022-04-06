## 安装
- ### npx  moon-template init my-app  
- ### 选择 uniapp

## 运行
- ### npm install
- ### manifest.json 重新获取appId
- ### 执行 npm run gulp 
- ### Hbuilder中右击项目选择识别项目
- ### 设置updateTemplate.config.js ， 执行 npm run updateTemplate  更新模板文件
> Hbuilder-运行
<br/>自定义模式
<br/>   公众号
  
## 第三方以H5形式接入应用
- ### 在应用菜单中配置第三方H5页面地址即可。
- ### 应用会对所有跳转的H5页面带上当前用户的token。
- ### 第三方依据当天用的token调用后端服务接口获取到当前用户信息
- ### H5端使用app原生功能API-[Html5+plus](https://uniapp.dcloud.io/)

## 打开微信小程序
- ### 在应用菜单中配置微信小程序的 原始id，appId，path，type 
- ### 应用会对所有跳转的微信小程序页面带上当前用户的token。
- ### 第三方依据当天用的token调用后端服务接口获取到当前用户信息，实现免登