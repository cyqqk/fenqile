<template>
	<div listBanner>
		<div class="title-wrap">
			<div class="detail-title">乐疯抢</div>
			<div class="time-wrap" id="floor__title_wrap">
				<span class="time-tip">距离本场结束</span>
				<span class="time-hour" role="timer" data-type="hour">{{ this.h }}</span>
				:
				<span class="time-min" role="timer" data-type="min">{{ this.m }}</span>
				:
				<span class="time-sec" role="timer" data-type="sec">{{ this.s }}</span>
			</div>
		</div>
		<swiper :options="swiperOption" class="swiper-wrap" ref="mySwiper" v-if="pictureArr.length != 0">
			<swiper-slide v-for="(item, index) in pictureArr" :key="index"><img :src="item.pictureUrl" alt="" /></swiper-slide>
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
			h: '00',
			m: '00',
			s: '00',
			pictureArr: [
				{
					pictureUrl: 'https://cimgs1.fenqile.com/product3/M00/35/59/RbQHAFuZhHKADKH7AAHUV66EiZw233_156x156.png',
					price: 5099,
					delPrice: 6499,
					title: '超级秒杀'
				},
				{
					pictureUrl: 'https://cimgs1.fenqile.com/product3/M00/95/37/RbQHAFvuOPeAMlxbAAEiW2WBHsw627_156x156.jpg',
					price: 45,
					delPrice: 149,
					title: '超级秒杀'
				},
				{
					pictureUrl: 'https://cimgs1.fenqile.com/product4/M00/07/52/gsMHAFzFYOCANOD0AAOTr4XZ4VM404_156x156.jpg',
					price: 395,
					delPrice: 790,
					title: '超级秒杀'
				},
				{
					pictureUrl: 'https://cimgs1.fenqile.com/product4/M00/03/07/gcMHAFyixFaAACB-AAbxEpQ9gU0676_156x156.jpg',
					price: 79,
					delPrice: 299,
					title: ''
				},
				{
					pictureUrl: 'https://cimgs1.fenqile.com/product4/M00/03/A6/gcMHAFyq70iAMVPuAAKc6h6XIHE831_156x156.jpg',
					price: 139,
					delPrice: 408,
					title: ''
				},
				{
					pictureUrl: 'https://cimgs1.fenqile.com/product4/M00/0A/AC/g8MHAFzRatuAbsHnAAF_hL0KTVA810_156x156.jpg',
					price: 449,
					delPrice: 659,
					title: ''
				},
				{
					pictureUrl: 'https://cimgs1.fenqile.com/product/M00/EE/CC/hRoGAFqh5lCAZfkBAADiax0jJF0789_156x156.jpg',
					price: 69,
					delPrice: 89,
					title: ''
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
	created() {
		// 第一次请求
		this.countTime();
	},
	methods: {
		countTime() {
			//获取当前时间
			let date = new Date();
			let now = date.getTime();
			//设置截止时间
			let endDate = new Date('2019-06-20 08:00:00');
			let end = endDate.getTime();
			//时间差
			let leftTime = end - now;
			//定义变量 d,h,m,s保存倒计时的时间
			if (leftTime >= 0) {
				this.h = Math.floor((leftTime / 1000 / 60 / 60) % 24);
				if (this.h < 10) {
					this.h = '0' + this.h;
				}
				this.m = Math.floor((leftTime / 1000 / 60) % 60);
				if (this.m < 10) {
					this.m = '0' + this.m;
				}
				this.s = Math.floor((leftTime / 1000) % 60);
				if (this.s < 10) {
					this.s = '0' + this.s;
				}
			}
			//递归每秒调用countTime方法，显示动态时间效果
			setTimeout(this.countTime, 1000);
		}
	}
});
</script>

<style>
.title-wrap {
	padding: 0 1rem;
	height: 4rem;
	background: #fff;
	position: relative;
	display: -webkit-box;
	display: box;
	-webkit-box-align: center;
	box-align: center;
}
.title-wrap .detail-title {
	-webkit-box-flex: 1;
	-webkit-flex: 1;
	-ms-flex: 1;
	flex: 1;
	font-size: 1rem;
	font-weight: 500;
	color: #25324e;
}
.time-wrap {
	color: #e3e4e8;
	display: flex;
}
.time-wrap .time-tip {
	display: block;
	font-size: 0.8125rem;
	color: #979dab;
	line-height: 1.25rem;
	margin-right: 0.25rem;
}
.time-wrap .time-hour,
.time-wrap .time-min,
.time-wrap .time-sec {
	display: block;
	width: 1.375rem;
	height: 1.25rem;
	background: #3c3f56;
	border-radius: 0.125rem;
	display: box;
	display: -webkit-box;
	display: -moz-box;
	-webkit-box-pack: center;
	-moz-box-pack: center;
	-webkit-box-align: center;
	-moz-box-align: center;
	color: #fff;
	font-size: 0.875rem;
	font-weight: 700;
	overflow: hidden;
	position: relative;
}
.time-wrap .time-hour {
	margin-right: 0.25rem;
}
</style>
