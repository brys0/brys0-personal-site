<script setup lang="ts">
import LightableSVG from '~/assets/lightable.svg';
import MusicPlayer from '~/assets/music-player.png';
import SpotifyWebServer from '~/assets/spotify-web-server.png';
import PersonalSite from '~/assets/personal-site.png';
import { PhGithubLogo, PhLink, PhDisc, PhChats, PhSpotifyLogo, PhConfetti } from '@dnlsndr/vue-phosphor-icons';


const openPage = (page: string) => {
    window.open(page, '_blank');
}
useHead({
    title: 'Brys\' Site -> Projects',
    htmlAttrs: {
        lang: 'en'
    },
    meta: [
        {
            name: 'description', 
            content: 'Projects page'
        },
        {
            content: 'Brys\' Personal Site > Projects',
            property: 'og:title'
        },
        {
            property: 'og:description',
            content: 'Projects page.. lol'
        },
    ]
})
</script>

<template>
    <div class="flex col p-8" id="projects">
            <div class="project-group flex row wrap" style="--i: 1">
                <div class="card-container">
                    <Card :image="LightableSVG" :height="273" :width="426">
                        <template #header>
                            <h1 class="text calib large" tiny="true">Lightable</h1>
                        </template>
                        <template #content>
                            <p class="text titl">Open-source Chat Reimagined</p>
                        </template>
                    </Card>
                </div>
                <div class="info p-4 text white flex col">
                    <div class="icon">
                        <PhChats size="32" weight="duotone" color="var(--accent)" />
                    </div>
                    <h2 class="flex js-space">Lightable</h2>
                    <span class="text gray titl">Lightable is a cross-platform application to chat with your friends.<br>You can meet new people, or join a community of friends.<br>Everything is entirely open-source.<br />The sky is the limit, sign-up today!</span>
                    <div class="down flex row">
                        <IconButton class="default" @click="openPage('https://github.com/Lightable/Lightable')" aria-label="Github Page For Lightable" aria-describedby="Website Link">
                            <PhGithubLogo size="24" weight="duotone" />
                        </IconButton>
                        <IconButton class="default" @click="openPage('https://lightable.app/?ref=personal-site')" aria-label="Lightable Website" aria-describedby="Website Link">
                            <PhLink size="24" weight="duotone" />
                        </IconButton>
                    </div>

                </div>
            </div>
            <div class="project-group flex row wrap" style="--i: 1.5">
                <div class="card-container">
                    <Card :image="MusicPlayer" :height="273" :width="426">
                        <template #header>
                            <h1 class="text calib large" tiny="true">Music Player</h1>
                        </template>
                        <template #content>
                            <p class="text titl">Basic Music Player, Coding Challenge</p>
                        </template>
                    </Card>
                </div>
                <div class="info p-4 text white flex col">
                    <div class="icon">
                        <PhDisc size="32" weight="duotone" color="var(--red)" class="spin" />
                    </div>
                    <h2 class="flex js-space">Br4d's Music Player</h2>
                    <span class="text gray titl">A simple and basic music player app, built as a coding challenge</span>
                    <div class="down flex row">
                        <IconButton class="default" aria-label="Github Page For Br4d's Music Player" aria-describedby="Website Link">
                            <PhGithubLogo size="24" weight="duotone" @click="openPage('https://github.com/br4dw/music-player')" />
                        </IconButton>
                    </div>

                </div>
            </div>
            <div class="project-group flex row wrap" style="--i: 2">
                <div class="card-container">
                    <Card :image="SpotifyWebServer" :height="273" :width="426">
                        <template #header>
                            <h1 class="text calib large" tiny="true">Spotify Web</h1>
                        </template>
                        <template #content>
                            <p class="text titl">A simple and easy to use webserver for Spotify</p>
                        </template>
                    </Card>
                </div>
                <div class="info p-4 text white flex col">
                    <div class="icon">
                        <PhSpotifyLogo size="32" weight="duotone" color="var(--spotify)" />
                    </div>
                    <h2 class="flex js-space">Spotify Web</h2>
                    <span class="text gray titl">A proxy & caching layer for Spotify API requests.<br>With concise payloads and perdictable errors.</span>
                    <div class="down flex row">
                        <IconButton class="default" aria-label="Github page for Spotify Web" aria-describedby="Website Link">
                            <PhGithubLogo size="24" weight="duotone" @click="openPage('https://github.com/brys0/Spotify-Web')" />
                        </IconButton>
                    </div>

                </div>
            </div>
            <div class="project-group flex row wrap" style="--i: 2.5">
                <div class="card-container">
                    <Card :image="PersonalSite" :height="273" :width="426">
                        <template #header>
                            <h1 class="text calib large" tiny="true">Personal Site</h1>
                        </template>
                        <template #content>
                            <p class="text titl">No need to explain this</p>
                        </template>
                    </Card>
                </div>
                <div class="info p-4 text white flex col">
                    <div class="icon">
                        <PhConfetti size="32" weight="duotone" color="var(--info)" />
                    </div>
                    <h2 class="flex js-space">This Site</h2>
                    <span class="text gray titl">Self explanatory</span>
                    <div class="down flex row">
                        <IconButton class="default" aria-label="Github Page For This Website" aria-describedby="Website Link" role="button">
                            <PhGithubLogo size="24" weight="duotone" @click="openPage('https://github.com/brys0/brys0-personal-site')" />
                        </IconButton>
                    </div>

                </div>
            </div>
    </div>
</template>


<style lang="scss" scoped>
#projects {
    gap: 32px;
}

.project-group {
    width: 80%;
    gap: 10em;
    animation: slide-right calc(250ms * var(--i)) ease;
    .info {
        position: relative;
        background-color: var(--card);
        width: fit-content;
        border-radius: .5rem;
        box-shadow: rgba(0, 0, 0, 0.66) 0 30px 60px 0;
        width: 500px;
        animation: slide-right calc(250ms * var(--i)) ease forwards;
        animation-delay: calc(var(--i) * 150ms);
        opacity: 0;
        h2 {
            margin-top: 5px;
        }

        .icon {
            position: absolute;
            right: 22px;
        }

        .down {
            margin-top: auto;
            width: 100%;
            gap: 24px;

        }
    }
}

@media only screen and (max-width: 1328px) {
    .project-group {
        width: 100%;
        gap: 4em;

        .card-container {
            width: 100%;
            height: 320px;
        }

        .info {
            width: 100%;
        }
    }
}

.spin {
    animation: spin 4s infinite linear;
}

@keyframes spin {
    from {
        -webkit-transform: rotate(0deg);
    }

    to {
        -webkit-transform: rotate(360deg);
    }
}

@keyframes slide-right {
    from {
        opacity: 0;
        transform: translateX(-250px);
    }
    to {
        opacity: 1;
        transform: translateX(0);
    }
}

</style>
