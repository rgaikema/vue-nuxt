<template>
	<div class="section">
	<div class="container">
		<h1 class="title">This is the about page</h1>
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
import { gsap } from "gsap";

export default {
	head: {
		title: "About page",
		meta: [
			{ hid: "description", name: "description", content: "About page description" }
		]
	},
	transition: {
		mode: "out-in",
		css: false,
		enter(el, done) {
			console.log("Enter to About");
			let tl = gsap.timeline({ onComplete: done }),
				title = el.querySelector(".title"),
				card = el.querySelector(".card");
			tl
				.add('start')
				.from(title, {
					duration: 1,
					x: "-50%",
					autoAlpha: 0,
					ease: "back.out(1.7)"
				}, 'start')

				.from(card, {
					duration: 1,
					x: "-50%",
					autoAlpha: 0,
					rotation: -90,
					ease: "back.out(1.7)"
				}, 'start');
		},
		leave(el, done) {
		console.log("leave from About");
		let tl = gsap.timeline({ onComplete: done }),
			title = el.querySelector(".title"),
			card = el.querySelector(".card");
		tl
			.add('start')
			.to(title,{
				duration: 1,
				x: "100%",
				opacity: 0,
				transformOrigin: "50% 50%",
				ease: "back.in(1.7)"
			}, 'start')

			.to(card, {
				duration: 1,
				x: "100%",
				opacity: 0,
				rotation: 90,
				transformOrigin: "50% 50%",
				ease: "back.in(1.7)"
			}, 'start');
		}
  	}
};
</script>
<style>

</style>
