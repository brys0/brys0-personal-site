<script setup lang="ts">
import { ref, computed, Ref } from 'vue';

const props = defineProps({
    image: String,
    width: Number,
    height: Number,
});

const data = ref({

    mouseX: 0,
    mouseY: 0,
    mouseLeaveDelay: null
});

const card = ref() as Ref<HTMLElement | null>;
const cardBGImage = computed(() => { return { backgroundImage: `url(${props.image})` } });


const cardBGTransform = computed(() => {
    let mousePX = (data.value.mouseX / props.width);
    let mousePY = (data.value.mouseY / props.height);
    const tX = mousePX * -40;
    const tY = mousePY * -40;
    return {
        transform: `translateX(${tX}px) translateY(${tY}px)`
    }
})

const cardStyle = computed(() => {
    let mousePX = (data.value.mouseX / props.width);
    let mousePY = (data.value.mouseY / props.height);
    const rX = mousePX * 30;
    const rY = mousePY * -30;
    return {
        transform: `rotateY(${rX}deg) rotateX(${rY}deg)`,
        height: props.height + 'px',
        width: props.width + 'px'
    }
})
const handleMouseMove = (e: MouseEvent) => {
    data.value.mouseX = e.pageX - card!!.value.offsetLeft - props.width / 2;
    data.value.mouseY = e.pageY - card!!.value.offsetTop - props.height / 2;
}

const handleMouseEnter = () => {
    clearTimeout(data.value.mouseLeaveDelay);
}

const handleMouseLeave = () => {
    data.value.mouseLeaveDelay = setTimeout(() => {
        data.value.mouseX = 0;
        data.value.mouseY = 0;
    }, 1000);
}
</script>

<template>
        <div class="card-wrap" @mousemove="handleMouseMove" @mouseenter="handleMouseEnter" @mouseleave="handleMouseLeave" ref="card">
            <div class="card" :style="cardStyle">
                <div class="card-bg" :style="[cardBGTransform, cardBGImage]"></div>
                <div class="card-info">
                    <slot name="header"></slot>
                    <slot name="content"></slot>
                </div>
            </div>
        </div>
</template>


<style lang="scss" scoped>
$hoverEasing: cubic-bezier(0.23, 1, 0.32, 1);
$returnEasing: cubic-bezier(0.445, 0.05, 0.55, 0.95);

.card-wrap {
    transform: perspective(800px);
    transform-style: preserve-3d;
    width: 100%;
    height: 100%;
    cursor: default;
    // background-color: #fff;

    &:hover {
        .card-info {
            transform: translateY(0);

        }

        .card-info p {
            opacity: 1;
        }

        .card-info,
        .card-info p {
            transition: 0.6s $hoverEasing;
        }

        .card-info:after {
            transition: 5s $hoverEasing;
            opacity: 1;
            transform: translateY(0);
        }

        .card-bg {
            transition:
                0.6s $hoverEasing,
                opacity 5s $hoverEasing;
            opacity: 0.8;
        }

        .card {
            transition:
                0.6s $hoverEasing,
                box-shadow 2s $hoverEasing;
            box-shadow:
                rgba(rgb(246, 152, 51), 0.2) 0 0 40px 5px,
                rgba(rgb(246, 152, 51), 0.2) 0 0 0 1px,
                rgba(black, 0.66) 0 30px 60px 0;
        }
    }
}

.card {
    position: relative;
    flex: 0 0 240px;

    background-color: var(--bg);
    overflow: hidden;
    border-radius: 10px;
    box-shadow: rgba(black, 0.66) 0 30px 60px 0;
    transition: 1s $returnEasing;
}

.card-bg {
    opacity: 0.5;
    position: absolute;
    top: -20px;
    left: -20px;
    width: 100%;
    height: 100%;
    padding: 20px;
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    transition:
        1s $returnEasing,
        opacity 5s 1s $returnEasing;
    pointer-events: none;
}

.card-info {
    padding: 20px;
    position: absolute;
    bottom: 0;
    color: #fff;
    transform: translateY(40%);
    transition: 0.6s 1.6s cubic-bezier(0.215, 0.61, 0.355, 1);

    p {
        opacity: 0;
        text-shadow: rgba(black, 1) 0 2px 3px;
        transition: 0.6s 1.6s cubic-bezier(0.215, 0.61, 0.355, 1);
    }

    * {
        position: relative;
        z-index: 1;
    }

    &:after {
        content: '';
        position: absolute;
        top: 0;
        left: 0;
        z-index: 0;
        width: 100%;
        height: 100%;
        opacity: 0;
        transform: translateY(100%);
        transition: 5s 1s $returnEasing;
    }
}

.card-info h1 {
    font-family: "Oswald";
    font-size: 36px;
    font-weight: 700;
    text-shadow: rgba(black, 0.5) 0 10px 10px;
}

@media only screen and (max-width: 604px) {
    .card {
        width: 100% !important;
        height: 100% !important;
    }
}
</style>