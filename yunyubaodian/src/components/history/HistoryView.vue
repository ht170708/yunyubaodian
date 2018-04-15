<template>
	<div class="history">
		
		<mt-header fixed title="历史记录">
			
		</mt-header>
		
		<div >
			<ul>
				<li v-for="item in arr" @click>
					{{item}}
				</li>
			</ul>
		</div>
		
	</div>
</template>

<script>
	
	export default {
		data() {
			return {
				val: '',
				arr: []
			}
		},
		mounted() {
			var ls = localStorage;
			var str = ''
			var val = ls.getItem("h")
			var arr = JSON.parse(val)
			console.log(str)
			arr.forEach(item => {
				str += 'a' + item
			});
			var brr = str.split('a')
			this.arr = brr

		}
	}
	
</script>

<style>
	.history{
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		margin-bottom: 40px;
	}
	ul{
		margin-top: 40px;
	}
</style>