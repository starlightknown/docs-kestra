<template>
    <div class="container-fluid bg-dark-4">
        <div class="container">
            <div class="container-title mb-4">
                <h2 class="title">Let Your Orchestrator Adapt to <span>Your Code</span>, Not the Reverse</h2>
            </div>
            <div class="row mb-5 align-items-center justify-content-between">
                <div class="col-md-5 order-1 order-md-1"
                     data-aos="fade-left">
                    <h3>Zero Modifications, Full Integration</h3>
                    <p v-for="desc in description">{{desc}}</p>
                </div>
                <div class="col-md-6 order-0 order-md-0 mask mb-3" data-aos="fade-left">
                    <NuxtImg
                        loading="lazy"
                        format="webp"
                        width="627px"
                        height="460px"
                        class="img-fluid"
                        :src="source"
                        alt="Zero Modifications"
                    />
                </div>
            </div>
        </div>
    </div>
</template>

<script>
  export default {
    props: {
      title: {
        type: String,
        default: undefined,
      },
      description: {
        type: Array,
        default: null,
        required: true,
      },
      source: {
        type: String,
        default: undefined,
      },
    },
  }
</script>

<style scoped lang="scss">
    @import "../../../../assets/styles/variable";

    .container-fluid {
        position: relative;
        z-index: 1;

        .container {
            border-bottom: $block-border;

            .container-title {
                padding-top: calc($spacer * 4);
                width: 100%;
                display: flex;
                justify-content: center;

                .title {
                    text-align: center;
                    font-size: 50px;
                    font-weight: 500;
                    text-align: center;
                    color: $white;

                    @include media-breakpoint-up(lg) {
                        max-width: 44%;
                        line-height: 50px;
                    }

                    span {
                        background: linear-gradient(90.03deg, #E151F7 2.16%, #5C47F5 65.09%);
                        background-clip: text;
                        -webkit-background-clip: text;
                        -webkit-text-fill-color: transparent;
                        color: $white;
                    }
                }
            }

            h3 {
                color: $white;
                font-size: $h2-font-size;
                font-weight: 300;
            }

            p, ul {
                color: $white-1;
                font-size: $font-size-md;
                font-weight: 300;

                b {
                    color: $white;
                    font-weight: 600;
                }
            }

            .mask {

                position: relative;

                & > img {
                    z-index: 10;
                }

                &::after {
                    width: calc($spacer * 15);
                    height: calc($spacer * 15);
                    position: absolute;
                    content: "";
                    right: 214px;
                    bottom: 142px;
                    z-index: -2;
                    background: linear-gradient(180deg, rgba(98, 24, 255, 0.00) 0%, #6117FF 100%);
                    filter: blur(65px);

                    @include media-breakpoint-down(lg) {
                        right: 38px;
                        bottom: 51px;
                    }

                    @include media-breakpoint-down(md) {
                        right: 26px;
                    }
                }
            }
        }
    }

</style>