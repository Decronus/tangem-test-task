<template>
    <div class="ads-header">
        <img src="@/assets/images/gift-cut.png" alt="gift-cut" />

        <div class="ads-header__text">
            <span class="text__date">Black Friday<span>, 24-27 Nov</span></span>
            <span class="text__discount">10%OFF</span>
            <span class="text__code">Use code <span>10FRIDAY</span> at checkout</span>
        </div>

        <div class="ads-header__cta-block">
            <ButtonUI text="Shop now" />
            <CloseIcon />
        </div>
    </div>
</template>

<script>
import ButtonUI from '@/components/ui/ButtonUI.vue';
import CloseIcon from '@/components/icons/CloseIcon.vue';

export default {
    name: 'AdsHeader',
    components: { ButtonUI, CloseIcon },
};
</script>

<style lang="scss">
@import '@/assets/scss/variables';

.ads-header {
    position: relative;
    height: 54px;
    width: 100%;
    background-color: $bgColor;
    display: flex;
    justify-content: center;
    flex-direction: row;

    img {
        position: absolute;
        left: -8px;
    }

    .ads-header__text {
        display: flex;
        align-items: center;
        z-index: 5;

        span {
            font-size: 16px;
        }

        span:not(:last-child)::after {
            content: '';
            display: inline-flex;
            align-items: center;
            width: 3px;
            height: 3px;
            border-radius: 2px;
            background: rgba(255, 255, 255, 0.15);
            margin: 0 12px;
            vertical-align: middle;
        }

        .text__date {
            font-weight: 600;

            span {
                font-weight: 400;
            }
        }

        .text__discount,
        .text__code span {
            font-weight: 600;
            color: $accentColor;
        }
    }

    .ads-header__cta-block {
        position: absolute;
        right: 0;
        top: 50%;
        transform: translate(0, -50%);
        display: flex;
        align-items: center;
        gap: 14px;
        margin-right: 22px;

        .icon-wrap {
            cursor: pointer;
        }
    }
}
</style>
