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
                <NuxtLink to="/" class="link unset">Home</NuxtLink>
                <NuxtLink to="/about" class="link unset">About</NuxtLink>
                <NuxtLink to="/projects" class="link unset">Projects</NuxtLink>
            </div>
            <div class="nav-bar flex col p-4 text gray titl links" id="navbar-1">
                <NuxtLink to="/contact" class="link unset">Contact</NuxtLink>
                <NuxtLink to="/about" class="link unset">Education</NuxtLink>
                <NuxtLink to="/projects" class="link unset">Technologies</NuxtLink>
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