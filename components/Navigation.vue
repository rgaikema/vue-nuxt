<template>
	<header>
			<div class="logo">
				<nuxt-link exact to="/">LOGO</nuxt-link>
			</div>
			<nav class="header__nav">
				<nuxt-link exact to="/">Home</nuxt-link>
				<nuxt-link to="/about">About</nuxt-link>
				<nuxt-link to="/contact">Contact</nuxt-link>
			</nav>
	</header>
</template>

<style>

.header__nav a{
	padding: 1em 2em
}
</style>
