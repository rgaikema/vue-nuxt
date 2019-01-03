<template>
	<div class="container">
		<h1>Welcome!</h1>
	</div>
</template>
<script>
	import { TweenMax, Back } from 'gsap'

	export default {
		transition: {
			mode: 'in-out',
			css: false,
			beforeEnter (el) {
				console.log('beforeEnter')
				TweenMax.set(el, {
					x: '-100%'
				})
			},
			enter (el, done) {
				console.log('Enter')
				TweenMax.to(el, 1, {
					x: '0%',
					transformOrigin: '50% 50%',
					ease: Back.easeOut
				})
				done()
			},
			leave (el, done) {
				console.log('Leave')
				TweenMax.to(el, 1, {
					y: '100%',
					transformOrigin: '50% 50%',
					ease: Back.easeIn
				})
				done()
			}
		}
	}
</script>

<style>

	html, body {
		font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
		background: transparent;
		color: white;
		width: 100vw;
		height: 100vh;
	}

	a, a:visited {
		color: #3edada;
		text-decoration: none;
	}

	.container {
		padding: 60px;
		width: 100vw;
		height: 100vh;
		background: transparent;
	}
</style>