<template>

	<div>

		<mt-tabbar v-model="selected" fixed>
			<mt-tab-item id="首页">
				<router-link to='/home'>
					首页
				</router-link>
			</mt-tab-item>
			<mt-tab-item id="收藏">
				<router-link to='/fav'>
					收藏
				</router-link>
			</mt-tab-item>
			<mt-tab-item id="历史记录">
				<router-link to='/history'>
					历史记录
				</router-link>
			</mt-tab-item>
			<mt-tab-item id="设置">
				<router-link to='/config'>
					设置
				</router-link>
			</mt-tab-item>
		</mt-tabbar>

	</div>

</template>

<script>
	import { Tabbar, TabItem } from 'mint-ui';

	export default {

		data() {
			return {
				selected: ''
			}
		}
	}
</script>

<style>
	* {
		margin: 0;
		padding: 0;
		list-style: none;
		text-decoration: none;
	}
	
	a {
		height: 20px;
		line-height: 20px;
		font-size: 15px;
		color: #000000;
	}
	
	.mint-tab-item{
		height: 40px;
		padding: 0;
	}
	.mint-tab-item{
		background: #222;
	}
	.mint-tab-item-label{
		height: 40px;
		line-height: 40px;
	}
	.mint-tab-item-label a{
		color: white;
	}
	.mint-tabbar > .mint-tab-item.is-selected{
		box-shadow: 0 2px 8px #fff;
		background: black;
		transition: all 0.5s;
	}
</style>