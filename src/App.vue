<template>
    <div class="header-wrap">
        <AdsHeader v-if="adsHeaderVisibility" @close="adsHeaderVisibility = false" />
    </div>

    <div class="main-page">
        <div class="content" />
        <AdsBanner v-if="adsBannerVisibility" @click="closeAdsBanner" />
    </div>
</template>

<script>
import AdsHeader from '@/components/ads/AdsHeader.vue';
import AdsBanner from '@/components/ads/AdsBanner.vue';

export default {
    name: 'App',
    components: { AdsHeader, AdsBanner },

    data() {
        return {
            adsBannerVisibility: true,
            adsHeaderVisibility: true,
        };
    },

    mounted() {
        const adsBannerVisibility = localStorage.getItem('adsBannerVisibility');
        if (adsBannerVisibility === null || JSON.parse(adsBannerVisibility)) {
            this.handleAdsBannerOpacity();
        }
    },

    methods: {
        handleAdsBannerOpacity() {
            const header = document.querySelector('.header-wrap');
            const headerRect = header.getBoundingClientRect();
            const adsBanner = document.querySelector('.ads-banner');

            this.handleOpacity = () => {
                const scrollTop = window.scrollY;
                const opacity = scrollTop - headerRect.height;
                adsBanner.style.opacity = opacity < 0 ? 0 : opacity + '%';
            };

            window.addEventListener('scroll', this.handleOpacity);
        },
        closeAdsBanner() {
            this.adsBannerVisibility = false;
            localStorage.setItem('adsBannerVisibility', false);
            window.removeEventListener('scroll', this.handleOpacity);
        },
    },
};
</script>

<style lang="scss">
@import '@/assets/scss/global';

#app {
    font-family: Graphik LCG;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #ffffff;
}

.header-wrap {
    padding-top: 54px;
}

.main-page {
    height: 200vh;
    padding: 0 32px;

    .content {
        height: 559px;
    }

    .ads-banner {
        opacity: 0;
    }
}
</style>
