<template>
	<div class="column">
		<h1 class="title">Welcome!</h1>
		<div class="card">
			<h2>Title of card</h2>
			<p>Vestibulum id ligula porta felis euismod semper. Nullam id dolor id nibh ultricies vehicula ut id elit.</p>
			<button class="btn button is-primary">Click me</button>
		</div>
	</div>
</template>
<script>

import { gsap } from "gsap";

export default {
	head: {
		title: '🚀 Home Page',
		meta: [
			{ hid: 'description', name: 'description', content: 'Home page description' }
		]
	},
	transition: {
		mode: "out-in",
		css: false,
		enter(el, done) {
			console.log("Enter to index");
			let tl = gsap.timeline({ onComplete: done }),
				card = el.querySelector(".card"),
				title = el.querySelector(".title"),
				titleTwo = el.querySelector(".title_two");
			tl
				.add('start')
				.from([title, titleTwo], {
					duration: 1,
					x: "-50%",
					autoAlpha:0,
					transformOrigin: "50% 50%",
					ease: "back.out(1.7)"
				},'start')
				.from(card, {
					duration: 1,
					scale: .8,
					x: "-100%",
					transformOrigin: "50% 50%",
					ease: "back.inOut(1.7)"
				},'start+=.1')
				.from(card,{
					duration: 1,
					autoAlpha: 0,
					ease: "back.inOut(1.7)"
				},'start');
		},
		leave(el, done) {
			console.log("Leave Home");
			let tl = gsap.timeline({ onComplete: done }),
				card = el.querySelector(".card"),
				title = el.querySelector(".title"),
				titleTwo = el.querySelector(".title_two");
			tl
				.add('start')
				.to([title, titleTwo], {
					duration: 1,
					x: "100%",
					transformOrigin: "50% 50%",
					ease: "back.in(1.7)"
				}, 'start')
				.to(card, {
					duration: 1,
					scale: ".8",
					transformOrigin: "50% 50%",
					ease: "back.in(1.7)"
				}, 'start')
				.to(card, {
					duration: 1,
					opacity: 0,
					ease: "back.in(1.7)"
				}, 'start');

		}
	}
};
</script>

<style>
html,
body {
	background: transparent;
	color: #333;
	margin: 0;
	padding: 0;
	overflow: hidden;
}

a,
a:visited {
	color: #3edada;
	text-decoration: none;
}

.card {
	width: 33vw;
	background: #efefef;
	border-radius: 3px;
	padding: 20px;
	color: #333;
}
</style>
