<template>
	<div class="section">
	<div class="container">
		<h1 class="title">This is the product page</h1>
			<div class="card">
				<header class="card-header">
					<p class="card-header-title">Component</p>
					<a href="#" class="card-header-icon" aria-label="more options">
						<span class="icon">
							<i class="fas fa-angle-down" aria-hidden="true"></i>
						</span>
					</a>
				</header>
				<div class="card-content">
					<div class="content">
						Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus nec iaculis mauris.
						<a href="#" >@bulmaio</a>.
						<a href="#">#css</a>
						<a href="#">#responsive</a>
						<br>
						<time datetime="2016-1-1">11:09 PM - 1 Jan 2016</time>
					</div>
				</div>
				<footer class="card-footer">
					<a href="#" class="card-footer-item">Save</a>
					<a href="#" class="card-footer-item">Edit</a>
					<a href="#" class="card-footer-item">Delete</a>
				</footer>
			</div>
		</div>
	</div>
</template>
<script>
import { TweenMax, Back } from "gsap";

export default {
	head: {
		title: "Product page",
		meta: [
			{ hid: "description", name: "description", content: "Product page description" }
		]
	},
	transition: {
		mode: "out-in",
		css: false,
		enter(el, done) {
			console.log("Enter to Product");
			let tl = new TimelineMax({ onComplete: done }),
				title = el.querySelector(".title"),
				card = el.querySelector(".card");
			tl
				.add('start')
				.from(title, 1, {
					x: "-50%",
					opacity: 0,
					ease: Back.easeOut
				}, 'start')

				.from(card, 1, {
					x: "-50%",
					opacity: 0,
					rotation: -90,
					ease: Back.easeOut
				}, 'start');
		},
		leave(el, done) {
		console.log("leave from Product");
		let tl = new TimelineMax({ onComplete: done }),
			title = el.querySelector(".title"),
			card = el.querySelector(".card");
		tl
			.to(title, 1, {
				x: "100%",
				opacity: 0,
				transformOrigin: "50% 50%",
				ease: Back.easeIn
			}, 'start')

			.to(card, 1, {
				x: "100%",
				opacity: 0,
				rotation: 90,
				transformOrigin: "50% 50%",
				ease: Back.easeIn
			}, 'start');
		}
  	}
};
</script>
<style>
</style>
