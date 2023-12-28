<template>
    <button class="button" :class="{ secondary: secondary }">
        <slot />
    </button>
</template>

<script>
export default {
    name: 'ButtonUI',
    props: {
        secondary: {
            type: Boolean,
            default: false,
        },
    },
};
</script>

<style lang="scss">
@import '@/assets/scss/variables';

.button {
    font-size: 16px;
    font-weight: 500;
    padding: 10px 14px;
    background: #ffffff;
    border-radius: 100px;
    color: $bgColor;
    outline: none;
    border: none;
    cursor: pointer;
}

.button.secondary {
    padding: 12px 24px;
    border-radius: 14px;
    opacity: 0.9;
    background: rgba(255, 255, 255, 0.1);
    color: #ffffff;
}
</style>
