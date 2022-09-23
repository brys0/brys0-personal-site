<script setup lang="ts">
import { PhInstagramLogo } from '@dnlsndr/vue-phosphor-icons';
</script>

<template>
    <footer class="flex row tp-4 bp-4 lp-4 wrap card js-space" id="footer">
        <div class="flex col">
            <h2 class="text large oswald slight-bold white unset ns" id="footer-name">Brys</h2>
            <div class="flex row p-1" id="footer-socials">
                <span class="text small titl white unset gray ns">404, No bitches found</span>
            </div>
        </div>
        <nav class="flex row mr-8 text small titl white card gap-half ns" id="footer-navigation">
            <div class="nav-bar flex col p-4 text gray titl links" id="navbar-1">
                <a href="/" class="link unset active-link">Home</a>
                <a href="/about" class="link unset">About</a>
                <a href="/projects" class="link unset">Projects</a>
            </div>
            <div class="nav-bar flex col p-4 text gray titl links" id="navbar-1">
                <a href="/contact" class="link unset">Contact</a>
                <a href="/about" class="link unset">Education</a>
                <a href="/projects" class="link unset">Technologies</a>
            </div>
        </nav>
    </footer>
</template>


<style lang="scss" scoped>
#footer {
    width: calc(100vw - 1rem);
}

.large {
    font-size: 42px;
}

#footer-navigation {
    max-width: 100%;
    min-width: 25%;
}
</style>