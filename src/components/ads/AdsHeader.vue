<template>
    <div class="ads-header">
        <img src="@/assets/images/gift-cut.png" alt="gift-cut" />

        <div class="ads-header__text">
            <span class="text__date bullet">Black Friday<span>, 24-27 Nov</span></span>
            <span class="text__date mobile bullet">Black Friday,&nbsp;</span>
            <span class="text__discount bullet">10%OFF</span>
            <span class="text__code">
                <span>Use code</span> <span class="promo">10FRIDAY</span> <span>at checkout</span>
            </span>
        </div>

        <div class="ads-header__cta-block">
            <ButtonUI class="button">Shop now</ButtonUI>
            <ArrowIcon class="arrow-icon" />
            <CloseIcon class="close-icon" @click="$emit('close')" />
        </div>
    </div>
</template>

<script>
import ButtonUI from '@/components/ui/ButtonUI.vue';
import CloseIcon from '@/components/icons/CloseIcon.vue';
import ArrowIcon from '@/components/icons/ArrowIcon.vue';

export default {
    name: 'AdsHeader',
    components: { ButtonUI, CloseIcon, ArrowIcon },
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

        @media (max-width: 650px) {
            left: -65px;
        }
    }

    .ads-header__text {
        display: flex;
        align-items: center;
        z-index: 5;

        @media (max-width: 650px) {
            position: absolute;
            right: 72px;
            top: 50%;
            transform: translate(0, -50%);
        }

        span {
            font-size: 16px;
        }

        .bullet {
            &::after {
                content: '';
                display: inline-flex;
                align-items: center;
                width: 3px;
                height: 3px;
                border-radius: 2px;
                background: rgba(255, 255, 255, 0.15);
                margin: 0 12px;
                vertical-align: middle;

                @media (max-width: 650px) {
                    content: none;
                }
            }
        }

        .text__date {
            font-weight: 600;
            @media (max-width: 650px) {
                display: none;
            }

            span {
                font-weight: 400;

                @media (max-width: 950px) {
                    display: none;
                }
            }
        }

        .text__date.mobile {
            display: none;

            @media (max-width: 650px) {
                display: block;
            }
        }

        .text__discount,
        .text__code .promo {
            font-weight: 600;
            color: $accentColor;
        }

        .text__code {
            @media (max-width: 650px) {
                display: none;
            }

            span:last-child {
                @media (max-width: 950px) {
                    display: none;
                }
            }
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

        .button {
            @media (max-width: 650px) {
                display: none;
            }
        }

        .arrow-icon {
            display: none;
            @media (max-width: 650px) {
                display: block;
            }
        }

        .close-icon {
            @media (max-width: 950px) {
                display: none;
            }
        }
    }
}
</style>
