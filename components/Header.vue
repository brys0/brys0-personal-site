<script setup lang="ts">
import { ref, nextTick, onMounted } from 'vue';

const showRoutes = ref(false);

nextTick(() => {
    showRoutes.value = true;
});
</script>

<template>
    <header class="p-4 flex row js-space" id="page-header">
        <div class="logo">

        </div>
        <div class="routes flex row js-center ai-center">
            <TransitionGroup name="slide-fade">
                <NuxtLink to="/" class="route link text titl white flex row js-center ai-center" v-if="showRoutes" :style="{ '--i': 0 }">
                    <span class="green jb-mono">0.1</span><span>Home</span>
                </Nuxtlink>
                <NuxtLink to="/about" class="route link text titl white flex row js-center ai-center" v-if="showRoutes" :style="{ '--i': 10 }">
                    <span class="green jb-mono">0.2</span><span>About</span>
                </Nuxtlink>
                <NuxtLink to="/projects" class="route link text titl white flex row js-center ai-center" v-if="showRoutes" :style="{ '--i': 20 }">
                    <span class="green jb-mono">0.3</span><span>Projects</span>
                </Nuxtlink>
            </TransitionGroup>
        </div>
    </header>

</template>


<style lang="scss" scoped>
#page-header {
    position: absolute;
    backdrop-filter: blur(5px);
    width: 100vw;
    background-color: rgba(0, 0, 0, 0.156);
    height: 15px;

    .routes {
        margin-right: 50px;
        gap: 32px;

        .route {
            transition: transform calc(20ms * var(--i)) ease-out;
            gap: 4px;
            text-decoration: none;
            .green {
                color: #5bb19d;
            }
        }
    }
}


.slide-fade-enter-from {
    transform: translateY(-35px);
    opacity: 0.4;
}
</style>