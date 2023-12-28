<template>
    <div class="ads-banner">
        <div class="ads-banner__content">
            <span class="ads-banner__title">Black Friday</span>
            <span class="ads-banner__discount">10%OFF</span>
            <span class="ads-banner__code">Use code <span>10FRIDAY</span> at checkout</span>
            <ButtonUI secondary>Shop now <span class="add-text">through Monday</span></ButtonUI>
        </div>

        <CloseIcon />
    </div>
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
    position: relative;
    min-height: 349px;
    max-width: 600px;
    padding: 75px 30px 55px;
    background: url('@/assets/images/gift-full.png');
    background-size: cover;
    background-repeat: no-repeat;
    border-radius: 16px;
    box-shadow: 0px 4px 34px 0px rgba(0, 0, 0, 0.45);
    margin-left: auto;
    display: flex;
    justify-content: flex-end;

    @media (max-width: 600px) {
        margin: 0 -32px;
        border-radius: 0;
    }

    @media (max-width: 530px) {
        background-position: 50% 0;
    }

    @media (max-width: 430px) {
        background-position: 85% 0;
        justify-content: center;
    }

    .icon-wrap {
        position: absolute;
        top: 15px;
        right: 15px;
        cursor: pointer;
    }

    .ads-banner__content {
        display: flex;
        flex-direction: column;
        align-items: center;

        .ads-banner__title {
            font-size: 46px;
            font-weight: 500;
            letter-spacing: -1.84px;
            margin-bottom: 25px;
        }

        .ads-banner__discount {
            background-image: linear-gradient(to right, rgba(125, 83, 23, 1), rgba(237, 223, 149, 1));
            background-clip: text;
            color: transparent;
            font-size: 40px;
            font-weight: 500;
            letter-spacing: -1.6px;
            margin-bottom: 14px;
        }

        .ads-banner__code {
            color: $secondaryTextColor;
            font-size: 16px;
            font-weight: 500;
            letter-spacing: 0.08px;
            margin-bottom: 40px;

            span {
                color: $accentColor;
            }
        }

        .button .add-text {
            @media (max-width: 430px) {
                display: none;
            }
        }
    }
}
</style>
