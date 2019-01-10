<template>
	<div class="container">
		<h1 class="title">Welcome!</h1>
		<div class="card">
			<h2>Title of card</h2>
			<p>Vestibulum id ligula porta felis euismod semper. Nullam id dolor id nibh ultricies vehicula ut id elit.</p>
			<button class="btn">Click me</button>
		</div>
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
				var card = el.querySelector(".card");
				var title = el.querySelector(".title");
				TweenMax.set(title, {
					x: '-100%'
				})
				TweenMax.set(card, {
					y: '-100%'
				})
			},
			enter (el, done) {
				console.log('Enter')
				var card = el.querySelector(".card");
				var title = el.querySelector(".title");
				TweenMax.to(title, 1, {
					x: '0%',
					transformOrigin: '50% 50%',
					ease: Back.easeOut
				})
				TweenMax.to(card, 1, {
					y: '0%',
					transformOrigin: '50% 50%',
					ease: Back.easeOut
				})
				done()
			},
			leave (el, done) {
				console.log('Leave')
				var card = el.querySelector(".card");
				var title = el.querySelector(".title");
				TweenMax.to(title, 1, {
					x: '100%',
					transformOrigin: '50% 50%',
					ease: Back.easeIn
				})
				TweenMax.to(card, 1, {
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
		margin: 0;
		padding: 0;
		overflow: hidden;
	}

	a, a:visited {
		color: #3edada;
		text-decoration: none;
	}

	.container {
		padding: 60px;
		width: 100%;
		height: 100%;
		background: transparent;
	}

	.card {
		width: 33vw;
		background: #efefef;
		border-radius: 3px;
		padding: 20px;
		color: #333;
	}
</style>