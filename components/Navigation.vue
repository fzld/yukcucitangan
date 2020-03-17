<template>
    <nav class="navbar" role="navigation" aria-label="main navigation">
        <div class="navbar-brand">
            <nuxt-link to="/">
            <img src="/logo.png" height="80px" width="80px">
            </nuxt-link>
            <a role="button" class="navbar-burger" aria-label="menu" aria-expanded="false" @click="isOpen = !isOpen" v-bind:class="{'is-active': isOpen}">
                <span aria-hidden="true"></span>
                <span aria-hidden="true"></span>
                <span aria-hidden="true"></span>
            </a>
        </div>
        <div class="navbar-menu" v-bind:class="{'is-active': isOpen}">
            <div class="navbar-end">
                <nuxt-link to="/count" class="navbar-item">COVID-19 Count</nuxt-link>
                <nuxt-link to="/blogs" class="navbar-item">Blog</nuxt-link>
                <nuxt-link to="/about" class="navbar-item">Tentang Kami</nuxt-link>
                <p class="navbar-item">      </p>
            </div>
        </div>
    </nav>
</template>

<script>
export default {
    data: function() {
        return {
            isOpen: false
        }
    }
}
</script>