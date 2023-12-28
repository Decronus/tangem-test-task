<template>
    <div class="ads-banner"></div>
</template>

<script>
import ButtonUI from '@/components/ui/ButtonUI.vue';
import CloseIcon from '@/components/icons/CloseIcon.vue';

export default {
    name: 'AdsBanner',
    components: { ButtonUI, CloseIcon },
};
</script>

<style lang="scss">
@import '@/assets/scss/variables';

.ads-banner {
    min-height: 349px;
    max-width: 600px;
    background: url('@/assets/images/gift-full.png');
}
</style>
