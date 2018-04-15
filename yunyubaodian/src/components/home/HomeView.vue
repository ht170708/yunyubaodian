<template>
	
	<div class="home">
		
		<mt-header fixed title="孕育宝典">
			
		</mt-header>
		
		<div class="container">
			<ul>
				<li>
					<router-link to='/list/yunqian'>
						<img src="../../assets/img/pic1.png"/>
					</router-link>
				</li>
				<li>
					<router-link to='/list/yunzhong'>
						<img src="../../assets/img/pic2.png"/>
					</router-link>
				</li>
				<li>
					<router-link to='/list/chanqian'>
						<img src="../../assets/img/pic3.png"/>
					</router-link>
				</li>
				<li>
					<router-link to='/list/chanhou'>
						<img src="../../assets/img/pic4.png"/>
					</router-link>
				</li>
				<li>
					<router-link to='/list/chengzhang'>
						<img src="../../assets/img/pic5.png"/>
					</router-link>
				</li>
				<li>
					<router-link to='/list/fangzhi'>
						<img src="../../assets/img/pic6.png"/>
					</router-link>
				</li>
			</ul>
		</div>
		
	</div> 
	
</template>

<script>
	import { Header } from 'mint-ui';
	export default{
		
	}
</script>

<style>
	.container ul li img{
		width: 80%;
		margin-left: auto;
		margin-right: auto;
		display: block;
		margin-top:10px ;
	}
	.home{
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
	}
</style>