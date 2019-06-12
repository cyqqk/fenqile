
<template>
	<div class="headerpt " id="header_wrap">
		<div class="header-wrap headerpt-fix" id="g_fix_header">
			<div class="header" id="g_index_header">

				<!-- 搜索框 -->
				<div class="search-header">
					<div class="search-wrap" id="search_wrap">
						<i class="iconfont wf-new-search js-theme-color"></i>
						<div class="search-inner">
							<div class="search-text" id="g_search_input" data-ad-id="" data-position-id="">
							</div>
						</div>
					</div>
					<!-- 消息换成购物车，有数字提示 @20171113 -->
					<a href="javascript:;" id="g_btn_go_cart" class="head-cart">
						<i class="icon-cart"></i>
						<span class="cart-num js-g-cart-num hide"></span>
					</a>
				</div>
				<!-- 搜索框 -->

			</div>
		</div>
	</div>
</template>

<script>
	import Vue from 'vue';
	export default Vue.extend({
		created() {
		}
	})
</script>

<style>
	.headerpt {
		padding-top: 2.8125rem;
	}

	.header {
		background-image: none;
		background-position: center bottom;
		background-repeat: no-repeat;
		background-size: cover;
		width: 100%;
	}

	.header {
		text-align: center;
		background-color: #fff;
		position: fixed;
		left: 0;
		top: 0;
		right: 0;
		z-index: 999;
		-webkit-transition: background-color .2s linear;
		transition: background-color .2s linear;
		background-image: linear-gradient(180deg, #e8eaee, #e8eaee, transparent 50%), linear-gradient(270deg, #e8eaee, #e8eaee 50%, transparent 50%), linear-gradient(0deg, #e8eaee, #e8eaee 50%, transparent 50%), linear-gradient(90deg, #e8eaee, #e8eaee 50%, transparent 50%);
		background-size: 100% 0, 0 100%, 100% 1px, 0 100%;
		background-repeat: no-repeat;
		background-position: top, right top, bottom, left top;
		max-width: 46.875rem;
		min-width: 20rem;
		margin: 0 auto;
		box-sizing: border-box;
	}

	.search-header {
		display: -webkit-flex;
		display: -ms-flexbox;
		display: flex;
		display: -webkit-box;
		display: box;
		-webkit-box-align: center;
		box-align: center;
		padding: 0 0.75rem;
		height: 2.8125rem;
	}

	.search-header .search-wrap {
		-webkit-box-flex: 1;
		-webkit-flex: 1;
		-ms-flex: 1;
		flex: 1;
		background-color: rgba(0, 0, 0, .05);
		height: 2rem;
		display: -webkit-flex;
		display: -ms-flexbox;
		display: flex;
		display: -webkit-box;
		display: box;
		-webkit-box-align: center;
		box-align: center;
		border-radius: 4px;
	}

	.wf-new-search {
		width: 1rem;
		height: 1rem;
		margin-left: 0.75rem;
		margin-right: 0.5rem;
		font-size: 1rem;
		color: #a1a5b1;
		margin-top: 0.1875rem;
	}

	.iconfont {
		line-height: 1em;
		font-family: iconfont;
		-webkit-font-smoothing: antialiased;
		font-smoothing: antialiased;
		content: '';
		font-style: normal;
		font-weight: 400;
		speak: none;
		display: inline-block;
		text-decoration: inherit;
		font-variant: normal;
		text-transform: none;
	}

	.search-header .search-wrap .search-inner {
		-webkit-box-flex: 1;
		-webkit-flex: 1;
		-ms-flex: 1;
		flex: 1;
	}

	.head-cart {
		margin-left: 0.5rem;
		padding: 0.25rem 0.1875rem;
		font-size: 1.25rem;
		color: #979dab;
		position: relative;
	}

	.head-cart .icon-cart {
		width: 1.25rem;
		height: 1.125rem;
		background-position: 0 -4.375rem;
	}

	.head-cart .cart-num {
		position: absolute;
		top: -0.125rem;
		right: -0.4375rem;
		display: inline-block;
		padding: 0.05rem;
		height: 1.75rem;
		line-height: 1.75rem;
		text-align: center;
		border-radius: 0.9375rem;
		font-size: 1.25rem;
		font-style: normal;
		color: #fff;
		letter-spacing: 0;
		background: #fe4979;
		border: 1px solid #fff;
		-webkit-transform: scale(0.5);
		transform: scale(0.5);
		-webkit-transform-origin: 100% 0;
		transform-origin: 100% 0;
	}

	.icon {
		width: 1em;
		height: 1em;
		vertical-align: -0.15em;
		fill: currentColor;
		overflow: hidden;
	}
</style>
