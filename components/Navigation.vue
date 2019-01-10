<template>
    <nav class="nav">
        <div class="nav_holder">
            <nuxt-link exact to="/">Home</nuxt-link>
            <nuxt-link to="/product">Product</nuxt-link>
            <nuxt-link to="/contact">Contact</nuxt-link>
        </div>
    </nav>
</template>
<style>
    .nav {
        position: absolute;
        left: 60px;
        top: 20px;
        z-index: 3;
    }
</style>
