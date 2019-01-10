<template>
	<div>
		<div class="bg_image full_page"></div>
		<div class="content full_page">
			<Navigation />
			<nuxt/>
		</div>
	</div>
</template>

<script>
	import Navigation from '~/components/Navigation.vue'

	export default {
		components: {
			Navigation
		}
	}
</script>

<style>
html {
	font-family: "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
	font-size: 16px;
	word-spacing: 1px;
	-ms-text-size-adjust: 100%;
	-webkit-text-size-adjust: 100%;
	-moz-osx-font-smoothing: grayscale;
	-webkit-font-smoothing: antialiased;
	box-sizing: border-box;
	margin: 0;
	padding: 0;
	
}

*, *:before, *:after {
	box-sizing: border-box;
	margin: 0;
}


.full_page {
	position: absolute;
	width: 100%;
	height: 100%;
	top: 0;
	left: 0
}
.bg_image {
	background-image: url('https://picsum.photos/1600/900/?blur');
	background-size: cover;
	z-index: 1;
}
.content {
	z-index: 2;
}
</style>

