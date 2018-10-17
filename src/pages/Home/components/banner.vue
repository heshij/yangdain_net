<template>
    <div class="banner">
        <swiper :options="swiperOption" ref="mySwiper" @someSwiperEvent="callback">
            <!-- slides -->
            <swiper-slide
                    v-for="item of imgList"
                    :key="item.id"
            ><img :src="item.url" alt="" class="image-item"></swiper-slide>
            <!-- Optional controls -->
            <div class="swiper-pagination" slot="pagination"></div>
            <!--<div class="swiper-button-prev" slot="button-prev"></div>-->
            <!--<div class="swiper-button-next" slot="button-next"></div>-->
            <!--<div class="swiper-scrollbar"   slot="scrollbar"></div>-->
        </swiper>
    </div>
</template>

<script>
    import 'swiper/dist/css/swiper.css'
    import {swiper, swiperSlide} from 'vue-awesome-swiper'

    export default {
        name: "banner",
        components: {
            swiper,
            swiperSlide
        },
        data() {
            return {
                imgList: [{
                    id: 1,
                    url: require('../../.././assets/images/banner01.jpg')
                }, {
                    id: 2,
                    url: require('../../.././assets/images/banner01.jpg')
                }, {
                    id: 3,
                    url: require('../../.././assets/images/banner01.jpg')
                }],
                swiperOption: {
                    pagination: {
                        el: '.swiper-pagination'
                    },
                    autoplay: {
                        stopOnLastSlide: true,
                        delay: 2000,
                        disableOnInteraction: false
                    },
                    loop: true
                },
                swiperSlides: [1, 2, 3]
            }
        }
    }
</script>

<style scoped>
    .banner {
        width: 750px;
        height: 474px;
    }

    .banner .swiper-slide .image-item {
        width: 750px;
        height: 474px;
    }

    .banner >>> .swiper-pagination-bullet {
        width: 20px;
        height: 20px;
        display: inline-block;
        background-color: #fff;
    }
</style>