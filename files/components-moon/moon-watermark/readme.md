#  moon-watermark

### 作者：闰月飞鸟；时间：2021/08/19
### 开发目的
-  封装页面水印组件
- 注意使用时，需要将父组件的包裹元素的position设置为relactive


### Props 
参数 |说明|类型|可选值|默认值
---|---|---|---|---
position|定位方式，注意absolute时，需要将父组件的包裹元素的position设置为relactive|String|fixed|absolute
text|水印文字|String|—|''
textStyle|文字样式|Object|—|{opacity: 0.6, color: '#ccc', fontSize: '1.3rem', width: '25%', padding: '20px 20px'}
num|水印数量|Number|-|200

 

