<template>
  <div class="container">
    <h1>This is the product page</h1>
  </div>
</template>
<script>
	import { TweenMax, Back } from 'gsap'

	export default {
		transition: {
			mode: 'in-out',
			css: false,
			beforeEnter (el) {
				TweenMax.set(el, {
					x: '-100%'
				})
			},
			enter (el, done) {
				TweenMax.to(el, 1, {
					x: '0%',
					transformOrigin: '50% 50%',
					ease: Back.easeOut
				})
				done()
			},
			leave (el, done) {
				TweenMax.to(el, 1, {
					x: '100%',
					transformOrigin: '50% 50%',
					ease: Back.easeIn
				})
				done()
			}
		}
	}
</script>
<style scoped>
  .container {
    background: transparent;
  }
</style>