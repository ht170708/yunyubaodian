<template>
	<div>

		<transition enter-active-class='animated fadeIn' leave-active-class='animated fadeOut'>
 
		<router-view></router-view>

		</transition>

		<footView>

		</footView>

	</div>
</template>

<script>
	import FootView from './components/common/FootView'

	import HomeView from './components/home/HomeView'

	export default {
		components: {
			FootView,
			HomeView
		}
	}
</script>

<style>

</style>