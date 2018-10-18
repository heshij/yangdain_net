<template>
    <div class="wrapList">
        <h2>
            <span class="iconfont">&#xe636;</span>
            <span>今日疯抢</span>
        </h2>
        <!--<ul >
            <li>
                <ul class="proList-items">
                    <li>
                        <router-link to="/">
                            <div class="image">
                                <img src="../../.././images/home/pro01.jpg" alt="" >
                            </div>
                            <div class="price">
                                <span>88</span>
                                <s>96</s>
                            </div>
                            <p>美国/SUPER MILD沐 浴露500ml</p>
                        </router-link>
                    </li>
                    &lt;!&ndash;<li></li>
                    <li></li>
                    <li></li>&ndash;&gt;
                </ul>
            </li>
        </ul>-->
        <swiper >
            <swiper-slide>

            </swiper-slide>
        </swiper>
    </div>
</template>

<script>
    import 'swiper/dist/css/swiper.css'
    import {swiper, swiperSlide} from 'vue-awesome-swiper'
    export default {
        name: "proList",
        components:{
            swiper,
            swiperSlide
        },
        data(){
            return{
                swiperOption: {},
                proList:[
                    {}
                ]
            }
        }
    }
</script>

<style scoped>
    .wrapList {
    }
    .wrapList h2{
        width: auto;
        height: 96px;
        line-height: 96px;
    }
    .wrapList .proList-items {
        width: 750px;
        height: auto;
        display: flex;
        justify-content: space-around;
    }

    .wrapList .proList-items li {
        width: 324px;
        height: 464px;
        border: 2px solid skyblue;
    }

    .wrapList .proList-items li .image {
        width: 324px;
        position: relative;
        padding-bottom: 100%;
    }
    .wrapList .proList-items li .image img{
        position: absolute;
        /*top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        margin: auto;*/
        width: 100%;
    }
</style>