<template>
	<div id="banner">
		<swiper :options="swiperOption" class="swiper-wrap" ref="mySwiper" v-if="banner.length != 0">
			<swiper-slide v-for="(item, index) in banner" :key="index"><img :src="item.image" alt="" /></swiper-slide>
			<!-- 常见的小圆点 -->
			<div class="swiper-pagination" v-for="(item, index) in banner" :key="index" slot="pagination"></div>
		</swiper>
	</div>
</template>
<script>
import Vue from 'vue';
import { swiper, swiperSlide } from 'vue-awesome-swiper';
require('swiper/dist/css/swiper.css');
export default Vue.extend({
	data() {
		const that = this;
		return {
			banner: [
				{
					image: 'https://cimgs1.fenqile.com/ibanner2/M00/37/CF/jqgHAFzwjiqARGpoAAI4V6DGdas870_750x320.jpg'
				},
				{
					image: 'https://cimgs1.fenqile.com/ibanner2/M00/37/CF/jqgHAFzwjiqARGpoAAI4V6DGdas870_750x320.jpg'
				},
				{
					image: 'https://cimgs1.fenqile.com/ibanner2/M00/38/B2/jagHAFz3vOaAC_BNAAC-onf10rA541_750x320.jpg'
				},
				{
					image: 'https://cimgs1.fenqile.com/ibanner2/M00/38/B3/jagHAFz4vEyALg3SAAE8xjGgRpo530_750x320.jpg'
				},
				{
					image: 'https://cimgs1.fenqile.com/ibanner2/M00/01/3C/j6gHAFxAa9SANOf8AAF6_QBmUBk640_750x320.jpg'
				}
			],
			imgIndex: 1,
			swiperOption: {
				//是一个组件自有属性，如果notNextTick设置为true，组件则不会通过NextTick来实例化swiper，也就意味着你可以在第一时间获取到swiper对象，假如你需要刚加载遍使用获取swiper对象来做什么事，那么这个属性一定要是true
				notNextTick: true,
				//循环
				loop: true,
				//设定初始化时slide的索引
				initialSlide: 0,
				//自动播放
				autoplay: {
					delay: 1500,
					stopOnLastSlide: false,
					/* 触摸滑动后是否继续轮播 */
					disableOnInteraction: false
				},
				//滑动速度
				speed: 800,
				//滑动方向
				direction: 'horizontal',
				//小手掌抓取滑动
				grabCursor: true,
				on: {
					//滑动之后回调函数
					slideChangeTransitionStart: function() {
						/* realIndex为滚动到当前的slide索引值 */
						that.imgIndex = this.realIndex - 1;
					}
				},
				//分页器设置
				pagination: {
					el: '.swiper-pagination',
					clickable: true,
					type: 'bullets'
				}
			}
		};
	},
	components: {
		swiper,
		swiperSlide
	}
});
</script>

<style scoped>
#banner img {
	cursor: pointer;
	width: 100%;
}
</style>
