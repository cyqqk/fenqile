<template>
	<div id="nav2">
		<ul>
			<li v-for="(item, index) in pictureArr">
				<a><img :src="item.pictureUrl" /></a>
			</li>
		</ul>
	</div>
</template>

<script>
import Vue from 'vue';
export default Vue.extend({
	data() {
		return {
			pictureArr: [
				{
					pictureUrl: 'https://cimgs1.fenqile.com/ibanner2/M00/37/DF/jqgHAFz46EeAffqjAAA5qkq9QMc315_344x144.png'
				},
				{
					pictureUrl: 'https://cimgs1.fenqile.com/ibanner2/M00/37/AA/jqgHAFzY0hiAOIu7AABjwWPWKEI422_344x144.png'
				},
				{
					pictureUrl: 'https://cimgs1.fenqile.com/ibanner2/M00/37/DF/jqgHAFz447OAQ7KDAAAxXzZJK_A189_344x144.jpg'
				},
				{
					pictureUrl: 'https://cimgs1.fenqile.com/ibanner2/M00/38/B3/jagHAFz4sICAX1KbAAAzJDdIybQ271_344x144.png'
				}
			]
		};
	}
});
</script>

<style lang="scss" scoped>
#nav2 {
	display: flex;
	width: 100%;
	li {
		display: inline-block;
		width: 50%;
		margin-top:4px; 
		img {
			width:100%;
			height: 100%;
		}
	}
}
</style>
