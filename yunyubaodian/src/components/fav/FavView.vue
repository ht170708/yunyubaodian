<template>

	<div class="fav">

		<mt-header fixed title="收藏">

		</mt-header>
		<div>
			<ul class="oul" >
				<li v-for="i in text">
					{{i}}
				</li>
			</ul>
		</div>

	</div>

</template>

<script>
	export default {
		data(){
			return{
				text:[]
			}
		},
		mounted() {
			let meStr = localStorage.getItem("f");

			let meBrr = JSON.parse(meStr);

			let meS = "";

			meBrr.forEach((val, idx) => {

				meS += "a"+val;

			})
			
			
			this.text = meS.split('a');
			
		}
	}
</script>

<style>
	.fav {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
	}
	.oul{
		margin-top: 40px;
		
	}
</style>