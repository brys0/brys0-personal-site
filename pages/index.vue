<script setup lang="ts">
import { onMounted, ref } from 'vue';

const backgroundY = ref(0);

const scrollMaxValue = () => {
    const body = document.body;
    const html = document.documentElement;

    const documentHeight = Math.max(
        body.scrollHeight,
        body.offsetHeight,
        html.clientHeight,
        html.scrollHeight,
        html.offsetHeight
    );

    const windowHeight = window.innerHeight;

    return documentHeight - windowHeight;
};

onMounted(() => {
    window.onscroll = () => {
        backgroundY.value = (window.scrollY / scrollMaxValue()) * 100;
    }
})

useHead({
    title: 'Brys\' Site',
    meta: [
        {
            name: 'description', 
            content: 'Home page of my site'
        },
        {
            content: 'Brys\' Personal Site',
            property: 'og:title'
        },
        {
            property: 'og:description',
            content: 'Home page of this mid site'
        },
    ]
})
</script>

<template>
    <div id="home-page" :style="`background-position-y: ${backgroundY}px;`">
        <section class="home-top flex col js-center lp-16 p-8" id="home-top">
            <h1 class="text large white ns titl">Brys0</h1>
            <span class="text white ns oswald space-5 large">A passionate & personal developer</span>
            <div class="about text ns space-5 gray rounded calib med" id="home-info">
                <p>
                    Self-taught, full-stack engineer, specializing in frontend design,
                    and backend management
                </p>
            </div>
            <div class="project-button">
                <Button class="primary disabled" @click="$router.push('/projects')">Check out my projects...</Button>
            </div>
        </section>

    </div>
</template>


<style lang="scss" scoped>
#home-page {
    // background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' version='1.1' xmlns:xlink='http://www.w3.org/1999/xlink' xmlns:svgjs='http://svgjs.com/svgjs' width='3440' height='1440' preserveAspectRatio='none' viewBox='0 0 3440 1440'%3e%3cg mask='url(%26quot%3b%23SvgjsMask1011%26quot%3b)' fill='none'%3e%3cpath d='M3548.352%2c1218.855C3664.219%2c1224.262%2c3777.78%2c1172.146%2c3838.608%2c1073.382C3902.39%2c969.822%2c3910.917%2c836.876%2c3847.546%2c733.064C3786.432%2c632.949%2c3665.641%2c596.835%2c3548.352%2c597.895C3433.241%2c598.935%2c3313.703%2c637.437%2c3258.38%2c738.388C3204.653%2c836.425%2c3243.747%2c952.603%2c3301.512%2c1048.317C3356.897%2c1140.087%2c3441.281%2c1213.858%2c3548.352%2c1218.855' fill='rgba(191%2c 85%2c 31%2c 0.4)' class='triangle-float3'%3e%3c/path%3e%3cpath d='M1982.015%2c610.091C2099.799%2c608.133%2c2221.652%2c581.032%2c2285.995%2c482.357C2356.017%2c374.972%2c2367.812%2c232.014%2c2299.13%2c123.767C2234.198%2c21.43%2c2103.185%2c5.86%2c1982.015%2c3.266C1854.241%2c0.531%2c1710.717%2c2.896%2c1640.479%2c109.668C1565.163%2c224.161%2c1582.757%2c379.568%2c1660.011%2c492.762C1729.033%2c593.893%2c1859.592%2c612.126%2c1982.015%2c610.091' fill='rgba(191%2c 85%2c 31%2c 0.4)' class='triangle-float1'%3e%3c/path%3e%3cpath d='M1201.380102612025 704.0165428499787L811.0795822808009 765.8340723210149 872.8971117518372 1156.134592652239 1263.1976320830613 1094.3170631812027z' fill='rgba(191%2c 85%2c 31%2c 0.4)' class='triangle-float2'%3e%3c/path%3e%3cpath d='M1047.534429997049 309.45201032627034L1463.5871959624947 302.189782282779 1456.3249679190033-113.8629836826666 1040.2722019535577-106.60075563917525z' fill='rgba(191%2c 85%2c 31%2c 0.4)' class='triangle-float3'%3e%3c/path%3e%3cpath d='M1522.356010818864 1267.9813084109185L1609.967148904963 1419.7282508849748 1793.7819935729979 1212.438072518798z' fill='rgba(191%2c 85%2c 31%2c 0.4)' class='triangle-float1'%3e%3c/path%3e%3cpath d='M2044.5480185907436 812.0887890196647L2109.3853044544035 1117.1242363107 2414.420751745439 1052.2869504470402 2349.583465881779 747.2515031560047z' fill='rgba(191%2c 85%2c 31%2c 0.4)' class='triangle-float1'%3e%3c/path%3e%3cpath d='M3278.1797747216497 389.6334755755491L2948.4098920894926 337.4030572789668 2896.1794737929104 667.1729399111239 3225.9493564250674 719.4033582077061z' fill='rgba(191%2c 85%2c 31%2c 0.4)' class='triangle-float2'%3e%3c/path%3e%3cpath d='M2380.232%2c902.828C2511.68%2c895.006%2c2583.397%2c762.202%2c2643.826%2c645.207C2697.689%2c540.924%2c2735.726%2c423.159%2c2681.843%2c318.886C2623.915%2c206.786%2c2506.381%2c132.199%2c2380.232%2c135.107C2258.372%2c137.916%2c2164.086%2c227.493%2c2101.78%2c332.257C2037.696%2c440.011%2c2001.076%2c567.512%2c2056.061%2c680.181C2117.682%2c806.447%2c2239.98%2c911.173%2c2380.232%2c902.828' fill='rgba(191%2c 85%2c 31%2c 0.4)' class='triangle-float1'%3e%3c/path%3e%3cpath d='M635.0196132711994 1034.125592259622L410.23370320254253 687.9856449857213 288.87966599729873 1258.9115023282789z' fill='rgba(191%2c 85%2c 31%2c 0.4)' class='triangle-float1'%3e%3c/path%3e%3cpath d='M3064.3230513377184 650.3023266521618L3000.8378641410636 290.259938688746 2640.7954761776477 353.74512588540085 2704.2806633743025 713.7875138488166z' fill='rgba(191%2c 85%2c 31%2c 0.4)' class='triangle-float3'%3e%3c/path%3e%3cpath d='M1302.7922936340924 1403.007922760827L1298.834065977761 1176.2412122037902 1072.0673554207242 1180.1994398601214 1076.0255830770557 1406.9661504171584z' fill='rgba(191%2c 85%2c 31%2c 0.4)' class='triangle-float2'%3e%3c/path%3e%3cpath d='M916.793%2c738.898C995.415%2c744.141%2c1068.04%2c694.951%2c1106.304%2c626.068C1143.515%2c559.081%2c1137.033%2c477.979%2c1098.537%2c411.723C1060.237%2c345.804%2c992.899%2c295.417%2c916.793%2c299.896C846.213%2c304.05%2c800.042%2c367.774%2c768.672%2c431.136C741.362%2c486.298%2c739.834%2c547.946%2c766.527%2c603.409C797.875%2c668.543%2c844.668%2c734.088%2c916.793%2c738.898' fill='rgba(191%2c 85%2c 31%2c 0.4)' class='triangle-float3'%3e%3c/path%3e%3cpath d='M182.621%2c758.577C229.843%2c761.286%2c285.351%2c763.438%2c310.201%2c723.192C335.731%2c681.845%2c312.812%2c630.455%2c287.249%2c589.128C263.359%2c550.507%2c228.031%2c517.448%2c182.621%2c516.942C136.457%2c516.427%2c95.865%2c546.156%2c73.875%2c586.749C52.91%2c625.45%2c54.567%2c672.685%2c78.105%2c709.877C100.135%2c744.686%2c141.494%2c756.218%2c182.621%2c758.577' fill='rgba(191%2c 85%2c 31%2c 0.4)' class='triangle-float2'%3e%3c/path%3e%3cpath d='M335.61 1405.72 a416.53 416.53 0 1 0 833.06 0 a416.53 416.53 0 1 0 -833.06 0z' fill='rgba(191%2c 85%2c 31%2c 0.4)' class='triangle-float3'%3e%3c/path%3e%3cpath d='M631.228036003068 1049.144031184531L708.5276962614462 1207.6318215650583 907.6095517030478 1012.4384359872274z' fill='rgba(191%2c 85%2c 31%2c 0.4)' class='triangle-float1'%3e%3c/path%3e%3cpath d='M986.2739002763989-62.24025146843L800.3860212325188-68.73159924383117 883.592939091357 213.3458932096895z' fill='rgba(191%2c 85%2c 31%2c 0.4)' class='triangle-float2'%3e%3c/path%3e%3cpath d='M543.0070103619099 1502.8424357193037L909.2580504155605 1587.398150834346 993.813765530603 1221.1471107806956 627.5627254769523 1136.5913956656532z' fill='rgba(191%2c 85%2c 31%2c 0.4)' class='triangle-float3'%3e%3c/path%3e%3cpath d='M2001.3883756064656 1257.518690592807L2001.3883756064656 892.305385242727 1636.1750702563857 1257.518690592807z' fill='rgba(191%2c 85%2c 31%2c 0.4)' class='triangle-float3'%3e%3c/path%3e%3cpath d='M219.719%2c424.137C312.728%2c425.286%2c407.99%2c391.531%2c454.08%2c310.737C499.835%2c230.531%2c475.424%2c134.388%2c431.276%2c53.286C384.587%2c-32.485%2c317.343%2c-117.325%2c219.719%2c-119.799C118.983%2c-122.352%2c35.822%2c-47.02%2c-11.263%2c42.071C-55.18%2c125.168%2c-53.45%2c224.636%2c-4.824%2c305.068C42.154%2c382.773%2c128.924%2c423.016%2c219.719%2c424.137' fill='rgba(191%2c 85%2c 31%2c 0.4)' class='triangle-float2'%3e%3c/path%3e%3cpath d='M1317.21 1240.63 a262.25 262.25 0 1 0 524.5 0 a262.25 262.25 0 1 0 -524.5 0z' fill='rgba(191%2c 85%2c 31%2c 0.4)' class='triangle-float1'%3e%3c/path%3e%3c/g%3e%3cdefs%3e%3cmask id='SvgjsMask1011'%3e%3crect width='3440' height='1440' fill='white'%3e%3c/rect%3e%3c/mask%3e%3cstyle%3e %40keyframes float1 %7b 0%25%7btransform: translate(0%2c 0)%7d 50%25%7btransform: translate(-10px%2c 0)%7d 100%25%7btransform: translate(0%2c 0)%7d %7d .triangle-float1 %7b animation: float1 5s infinite%3b %7d %40keyframes float2 %7b 0%25%7btransform: translate(0%2c 0)%7d 50%25%7btransform: translate(-5px%2c -5px)%7d 100%25%7btransform: translate(0%2c 0)%7d %7d .triangle-float2 %7b animation: float2 4s infinite%3b %7d %40keyframes float3 %7b 0%25%7btransform: translate(0%2c 0)%7d 50%25%7btransform: translate(0%2c -10px)%7d 100%25%7btransform: translate(0%2c 0)%7d %7d .triangle-float3 %7b animation: float3 6s infinite%3b %7d %3c/style%3e%3c/defs%3e%3c/svg%3e");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: bottom;
}


.large {
    font-size: 72px;

    &[tiny='true'] {
        font-size: 32px;
    }
}
</style>