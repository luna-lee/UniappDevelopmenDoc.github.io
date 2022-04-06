<div id="icon" style="display: flex;flex-wrap: wrap;" class="pageClass">
	<div style="padding:10px;line-height: 2em;">	uni默认字体库图标，存放在/static/fonts/uni.ttf目录下。通过全局引入的css设置@font-face，名称为uniicons。H5中直接通过font-family使用。App端使用原生导航栏的右侧按钮的图表。直接将text设置为所对应的图标Unicode编码即可。也可以使用外部图标库
	</div>
		<div
			style="width: 100px;margin-bottom: 10px;display: flex; flex-direction: column;"
			v-for="(value, index) in list"
			:key="index"
		>
			<span style="font-family: uniicons;font-size:25px">{{ value.code }}</span>
			{{ '\\ue' + value.name }}
		</div>
	</div>
<script>
new Vue({
	el: '#icon',
	data() {
		return {
			list: []
		};
	},
	mounted() {
		for (let i = 0; i <= 588; i++) {
			try {
				// 包装为JSON
				let dataJSON = '{"code": "' + '\\ue' + i + '" ,"name": "' + i + ' " }';
				// 使用JSON工具转换
				let objJSON = JSON.parse(dataJSON);
				this.list.push(objJSON);
			} catch (e) {
				//TODO handle the exception
				console.log(JSON.stringify(e));
			}
		}
		this.list = [
			...this.list.slice(0, 3),
			...this.list.slice(30, 33),
			...this.list.slice(100, 104),
			...this.list.slice(130, 134),
			...this.list.slice(160, 165),
			...this.list.slice(200, 204),
			...this.list.slice(232, 234),
			...this.list.slice(260, 261),
			...this.list.slice(263, 265),
			...this.list.slice(300, 312),
			...this.list.slice(334, 335),
			...this.list.slice(337, 343),
			...this.list.slice(360, 369),
			...this.list.slice(369, 373),
			...this.list.slice(400, 409),
			...this.list.slice(430, 431),
			...this.list.slice(432, 433),
			...this.list.slice(434, 436),
			...this.list.slice(437, 438),
			...this.list.slice(460, 461),
			...this.list.slice(462, 464),
			...this.list.slice(465, 466),
			...this.list.slice(467, 469),
			...this.list.slice(480, 500)
		];
	}
});
</script>

<style>
@font-face {
	font-family: uniicons;
	font-weight: normal;
	font-style: normal;
	src: url('./uni-icon/uni.ttf') format('truetype');
}
</style>