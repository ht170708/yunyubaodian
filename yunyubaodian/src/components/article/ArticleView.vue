<template>

	<div class="article">

		<mt-header :title="title">
			<mt-button icon="back" slot="left" @click='btn'>返回</mt-button>
			<div class="al" slot="right" @click='aaa'>
				<img src="../../assets/img/scc.png" class="img" />
			</div>
		</mt-header>

		{{content.content}}

	</div>

</template>

<script>
	export default {

		data() {
			return {
				content: "",
				title: ''
			}
		},
		methods: {
			btn() {
				this.$router.history.go(-1)
			},
			aaa() {
				var text = this.title;
				
				let arr = JSON.parse(localStorage.getItem("f"));
				if(arr.includes(text)) {
					alert("已经收藏过了")
				} else {
					arr.push(text)
					alert("恭喜！收藏成功")
				}

				localStorage.setItem('f', JSON.stringify(arr));
				
			}
		},
		
		mounted() {
			
			if(!localStorage.getItem("f")) {
				localStorage.setItem("f", "[]");
			}

			let names = this.$route.query.names;
			let idx = this.$route.query.idx;

			this.$http({
					method: "get",
					url: "/arList"
				})
				.then(res => {
					
					this.content = res.data[names]['fenlei'][idx]
					
					this.title = res.data[names]['fenlei'][idx].title
				})
		}
	}

</script>

<style>
	.article {
		width: 100%;
		position: absolute;
		left: 0;
		top: 0;
	}
</style>