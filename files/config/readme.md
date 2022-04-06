# 依据编译环境，uniapp只有两种环境，一种是开发环境，一种是生产环境。
- baseUrl 依据开发环境与生 产环境的配置，动态配置。
- 设置成全局对象uni.$globalConfig
- 发布测试版本，在production中修改即可
- proxy设置为true时，在dev的H5模式下，接口请求走代理模式 ,更改接口时，需要重新运行项目，不然代理的还是上个接口地址
- menuType设置菜单模式，localMenuTree 本地菜单，serviceMenuTree 服务端动态菜单