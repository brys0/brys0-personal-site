<template>
    <div class="flex col lp-16 p-8">
        <span class="text gray ns titl">Hi I'm</span>
        <h1 class="text large white ns titl unset bold">Brys</h1>
        <div class="content">
            <section class="section p-4">
                <h2 class="text white ns titl bold unset section-title">How it all started</h2>
                <div class="body flex col">
                    <span class="text gray ns titl">I started working with computers since I was a child.</span>
                    <div class="section-image rel">
                        <img src="~assets/about-me-start.jpg" class="section-image"/>
                        <span class="text gray titl abs" id="start-text-hint">Thats me! -></span>
                    </div>
                </div>
            </section>
        </div>
    </div>
</template>



<style lang="scss" scoped>
@import '../assets/main.scss';
.large {
    font-size: 72px;

    &[tiny='true'] {
        font-size: 32px;
    }
}
.section {
    margin-top: 40px;
    background-color: var(--card);
    border-radius: $round;
    .section-title {
        font-size: 32px;
    }
    .body {
        margin-top: 20px;
        
        .section-image {
            height: 240px;
            width: 420px;
            border-radius: $round;
        }
    }
}

#start-text-hint {
    left: 20px;
    top: 70px;
    color: var(--accent);
    font-weight: bold;
    background-color: var(--card);
    border-radius: $round-xl;
}
</style>