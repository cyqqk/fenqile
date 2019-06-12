<template>
	<div class="home">
		<Header />
		<IndexNav/>
		<Banner/>
		<IndexNav2/>
		<Discount/>
	</div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Header from '@/components/Header.vue';
import IndexNav from '@/components/IndexNav.vue';
import Banner from '@/components/Banner.vue';
import IndexNav2 from '@/components/IndexNav2.vue';
import Discount from '@/components/Discount.vue';
@Component({
	components: {
		Header,
		IndexNav,
		Banner,
		IndexNav2,
		Discount
	}
})
export default class Home extends Vue {}
</script>
