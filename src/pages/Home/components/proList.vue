<template>
    <div class="wrapList">
        <h2>
            <span class="iconfont" v-html="titleIcon"></span>
            <span>{{title}}</span>
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
        <swiper :options="swiperOption" tag="ul" class="proList-ul">
            <swiper-slide
                    tag="li"
                    class="porList-li"
                    v-for="(items,index) of proList"
                    :key="index"
            >
                <ul class="proList-items">
                    <li
                            v-for="item of items.listArray"
                            :key="item.id"
                    >
                        <router-link to="/">
                            <div class="image">
                                <img :src="item.imgUrl" alt="">
                            </div>
                            <div class="price">
                                <span class="new_price">{{ item.new_price | floatNums | rmb}}</span>
                                <span class="old_price">{{item.old_price | floatNums | rmb}}</span>
                            </div>
                            <p>{{item.proInfo | ellipsis}}</p>
                        </router-link>
                    </li>
                </ul>
            </swiper-slide>
        </swiper>
    </div>
</template>

<script>
    import 'swiper/dist/css/swiper.css'
    import {swiper, swiperSlide} from 'vue-awesome-swiper'

    export default {
        name: "proList",
        components: {
            swiper,
            swiperSlide
        },
        props: ["info"],
        data() {
            return {
                swiperOption: {},
                titleIcon: this.info.titleIcon,
                title: this.info.title,
                proList: this.info.proList,
            }
        },
        filters: {
            floatNums(val) {
                return val.toFixed(2)
            },
            rmb(val) {
                return "￥" + val
            },
            ellipsis(val) {
                const nums = 20;
                if (val.length > nums) {
                    return val.substring(0, nums) + "..."
                }
            }
        }
    }
</script>

<style scoped>
    .wrapList {
    }

    .wrapList h2 {
        width: auto;
        height: 96px;
        line-height: 96px;
        margin-left: 20px;
    }

    .wrapList h2 span:first-child {
        margin-right: 8px;
        font-size: 40px;
        /*color: #ff9900;*/
    }

    .wrapList h2 span:last-child {
        font-size: 28px;
        color: #333333;
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
        border: 2px solid #eeeeee;
    }

    .wrapList .proList-items li .image {
        width: 324px;
        position: relative;
        padding-bottom: 100%;
    }

    .wrapList .proList-items li .image img {
        position: absolute;
        /*top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        margin: auto;*/
        width: 100%;
    }

    .wrapList .proList-items li .price {
        height: 57px;
        display: flex;
        justify-content: space-around;
    }

    .proList-items li p {
        padding: 0 30px;
        font-size: 28px;
        color: #555555;
    }

    .new_price {
        font-size: 28px;
        color: #ffa002;
    }

    .old_price {
        font-size: 28px;
        color: #888888;
        text-decoration: line-through;
    }
</style>