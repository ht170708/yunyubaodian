<template>

	<div class="list">

		<mt-header :title="home_title">
			<router-link to="/" slot="left">
				<mt-button icon="back">返回</mt-button>
			</router-link>
			<mt-button icon="more" slot="right"></mt-button>
		</mt-header>

		<ul>
			<li v-for='(item,index) in arr' @click="history">

				<router-link :to="{
					path: '/article', 
					params: { userId: 123 },
					query:{
						names:str,
						idx:index
					}
				}">
				<img :src="require('../../assets/img/tu/'+item.img)" />
					{{item.title}}
				</router-link>

			</li>
		</ul>
	
	</div>
	
	
</template>

<script>
	import '../../mock/mock';
	
	
	export default {

		data() {
			return {
				arr: [],
				str: "",
				title:"",
				home_title:""
			}
		},
		methods: {			
			history() {
				var ls = localStorage;
				var num = ''
				if(!ls.getItem('h')) {
					var arr = ls.setItem('h', "[]")
				}				
					var brr = ls.getItem('h')
					brr = JSON.parse(brr)  
					brr.push(this.home_title)		
					console.log(brr)
					brr.forEach(item => {
						num += item
					});
					var jsondata = JSON.stringify(brr)
					ls.setItem("h", jsondata)
				}
			},
		mounted() {

			let id = this.$route.params.id;
			this.str = id;
			this.$http({
					method: "get",
					url: "/arList"
				})
				.then(res => {
					this.arr = res.data[id]['fenlei'];
					this.home_title = res.data[id].home_title
				})
		}
	}
</script>
<style scoped>
	ul li {
		font-size: 21px;
		padding: 10px;
		height: 60px;
		line-height: 60px;
	}
	.list{
		position: absolute;
		left: 0;
		top: 0;
		width: 100%;
	}
	img{
		width: 15%;
		float: left;
		margin-right: 2%;
	}
</style>