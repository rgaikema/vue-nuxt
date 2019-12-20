<template>
	<div class="section">
		<div class="container">
			<h1 class="title">This is the contact page</h1>
			<article class="message is-warning">
				<div class="message-header">
					<p>Hello World</p>
					<button class="delete" aria-label="delete"></button>
				</div>
				<div class="message-body">
					Lorem ipsum dolor sit amet, consectetur adipiscing elit. <strong>Pellentesque risus mi</strong>, tempus quis placerat ut, porta nec nulla. Vestibulum rhoncus ac ex sit amet fringilla. Nullam gravida purus diam, et dictum <a>felis venenatis</a> efficitur. Aenean ac <em>eleifend lacus</em>, in mollis lectus. Donec sodales, arcu et sollicitudin porttitor, tortor urna tempor ligula, id porttitor mi magna a neque. Donec dui urna, vehicula et sem eget, facilisis sodales sem.
				</div>
			</article>
		</div>
	</div>
</template>

<script>
	import { gsap} from 'gsap'

	export default {
		head: {
			title: 'Contact page',
			meta: [
				{ hid: 'description', name: 'description', content: 'Contact page description' }
			]
		},
		transition: {
			mode: "out-in",
			css: false,
			enter(el, done) {
				console.log("Enter to Contact");
				let tl = gsap.timeline({ onComplete: done }),
					title = el.querySelector(".title"),
					message = el.querySelector(".message");
				tl
					.add('start')
					.from(title, {
						duration: 1,
						x: "-50%",
						autoAlpha: 0,
						ease: "back.out(1.7)"
					}, 'start')

					.from(message, {
						duration: 1,
						y: "-50%",
						autoAlpha: 0,
						ease: "back.out(1.7)"
					}, 'start');
			},
			leave(el, done) {
				console.log("leave from Contact");
				let tl = gsap.timeline({ onComplete: done }),
					title = el.querySelector(".title"),
					message = el.querySelector(".message");
				tl
					.to(title, {
						duration: 1,
						x: "100%",
						opacity: 0,
						transformOrigin: "50% 50%",
						ease: "back.in(1.7)"
					}, 'start')

					.to(message, {
						duration: 1,
						y: "100%",
						opacity: 0,
						transformOrigin: "50% 50%",
						ease: "back.in(1.7)"
					}, 'start');
			}
		}
	}
</script>

<style>

	.message {
		visibility: hidden;
	}

</style>
