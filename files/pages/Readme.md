# 页面文件
- 解决由于项目页面太多导致根目录下的pages.json文件维护不方便的问题，
- 这里引入gulp 自动监听pages目录下的first-page.json及所有page.json文件。 并以template.pages.json为模板文件进行合并生成pages.json  
- 当需要注册页面时，只需在页面文件目录下添加page.json 即可。内容参照官方写法。