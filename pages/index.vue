<template>
	<div class="section">
		<div class="container">
			<div class="columns">
				<div class="column">
					<h1 class="title">Welcome!</h1>
					<div class="card">
						<h2>Title of card</h2>
						<p>Vestibulum id ligula porta felis euismod semper. Nullam id dolor id nibh ultricies vehicula ut id elit.</p>
						<button class="btn button is-primary">Click me</button>
					</div>
				</div>
				<div class="column">
					<h2 class="title_two">Second column</h2>
				</div>
			</div>
		</div>
	</div>
</template>
<script>

import { TweenMax, Back } from "gsap";

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
			let tl = new TimelineMax({ onComplete: done }),
				card = el.querySelector(".card"),
				title = el.querySelector(".title"),
				titleTwo = el.querySelector(".title_two");
			tl
				.add('start')
				.from([title, titleTwo], 1, {
					x: "-50%",
					transformOrigin: "50% 50%",
					ease: Back.easeOut
				},'start')
				.from(card, 1, {
					scale: .8,
					transformOrigin: "50% 50%",
					ease: Back.easeOut
				},'start')
				.from(card, 1, {
					opacity: 0,
					ease: Back.easeOut
				},'start');
		},
		leave(el, done) {
			console.log("Leave Home");
			let tl = new TimelineMax({ onComplete: done }),
				card = el.querySelector(".card"),
				title = el.querySelector(".title"),
				titleTwo = el.querySelector(".title_two");
			tl
				.add('start)')
				.to([title, titleTwo], 1, {
					x: "100%",
					transformOrigin: "50% 50%",
					ease: Back.easeIn
				}, 'start')
				.to(card, 1, {
					scale: ".8",
					transformOrigin: "50% 50%",
					ease: Back.easeIn
				}, 'start')
				.to(card, 1, {
					opacity: 0,
					ease: Back.easeIn
				}, 'start');

		}
	}
};
</script>

<style>
html,
body {
	font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
		"Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
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
