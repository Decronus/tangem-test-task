<template>
    <div class="main-page">
        <AdsHeader />
    </div>
</template>

<script>
import AdsHeader from '@/components/ads/AdsHeader.vue';

export default {
    name: 'App',
    components: { AdsHeader },
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

.main-page {
    height: 200vh;
}
</style>
