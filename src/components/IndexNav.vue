<template>
	<div id="nav">
		<ul class="index-nav clear js-change-background js-need-handle">
			<li v-for="(item, index) in arr1">
				<a>
					<img class="imgauto" :src="item.pictureUrl" />
					<span class="js-change-font-color">{{ item.title }}</span>
				</a>
			</li>
		</ul>
		<ul class="poster">
			<li v-for="item in arr2">
				<a><img class="imgauto" :src="item" /></a>
			</li>
		</ul>
	</div>
</template>

<script>
import Vue from 'vue';
export default Vue.extend({
	data() {
		return {
			arr1: [
				{
					pictureUrl: 'https://cimgs1.fenqile.com/ibanner2/M00/37/D4/jqgHAFzxCHaAZ-IhAAAdZ-7ssB0545_96x96.png',
					title: '小赚一笔'
				},
				{
					pictureUrl: 'https://cimgs1.fenqile.com/ibanner2/M00/01/33/j6gHAFw3CWOAYIniAAAhq_2zi-A704_96x96.png',
					title: '旅游出行'
				},
				{
					pictureUrl: 'https://cimgs1.fenqile.com/ibanner2/M00/01/33/j6gHAFw3CWOAYIniAAAhq_2zi-A704_96x96.png',
					title: '乐花借钱'
				},
				{
					pictureUrl: 'https://cimgs1.fenqile.com/ibanner/M00/02/B3/wicJAFnvBDqAF7gCAAAaz3hmlmI290_96x96.png',
					title: '乐还款'
				},
				{
					pictureUrl: 'https://cimgs1.fenqile.com/ibanner/M00/02/B3/wicJAFnvBE-AUniGAAAiogTEaHo835_96x96.png',
					title: '娱乐充值'
				}
			],
			arr2: [
				'https://cimgs1.fenqile.com/ibanner2/M00/38/B3/jagHAFz41XqATWdPAAA_cQRZ7qg408_375x240.jpg',
				'https://cimgs1.fenqile.com/ibanner2/M00/06/47/j6gHAFz41iqAGF19AABJwMuAxgo584_375x240.jpg',
				'https://cimgs1.fenqile.com/ibanner2/M00/06/47/j6gHAFz41mOAHpfdAABMqTYz0tY691_375x240.jpg'
			]
		};
	}
});
</script>

<style>
#nav {
	margin: 0 auto;
}
.index-nav {
	width: 100%;
	background-color: #fff;
	background-image: none;
	background-position: center top;
	background-repeat: no-repeat;
	background-size: cover;
	position: relative;
}
.index-nav li {
	width: 20%;
	float: left;
	height: 5.75rem;
	display: box;
	display: -webkit-box;
	display: -moz-box;
	-webkit-box-pack: center;
	-moz-box-pack: center;
	-webkit-box-align: center;
	-moz-box-align: center;
	text-align: center;
}
.index-nav li a {
	cursor: pointer;
	width: 100%;
	display: block;
	color: #757c8e;
	font-size: 0.75rem;
	line-height: 0.875rem;
	overflow: hidden;
	text-overflow: ellipsis;
	white-space: nowrap;
	text-decoration: none;
}
.index-nav li img {
	width: 3rem;
	height: 3rem;
	margin: 0 auto 0.25rem;
	background: 0 0;
}

.imgauto,
.img-auto {
	display: block;
	height: auto;
	max-width: 100%;
	margin: 0 auto;
}
.index-nav li a {
	width: 100%;
	display: block;
	color: #757c8e;
	font-size: 0.75rem;
	line-height: 0.875rem;
	overflow: hidden;
	text-overflow: ellipsis;
	white-space: nowrap;
}
.poster {
	display: flex;
	width: 100%;
}
</style>
