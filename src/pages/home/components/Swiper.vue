<template>
    <div class="wrapper">
        <swiper :options="swiperOption" v-if="showSwiper">
            <!-- slides -->
            <swiper-slide v-for="item of list" :key="item.id">
                <img  class="swiper-img" :src="item.imgUrl"/>
            </swiper-slide>
            <div class="swiper-pagination"  slot="pagination"></div>
        </swiper>
    </div>
</template>

<script>
    export default {
        name: 'HomeSwiper',
        props: {
            list: Array
        },
        data () {
            return {
                swiperOption: {
                    pagination: '.swiper-pagination',
                    loop: true,
                    autoplay: 5000,
                    observer:true,//修改swiper自己或子元素时，自动初始化swiper
                    observeParents:true//修改swiper的父元素时，自动初始化swiper
                }
            }
        },
        computed: {
            showSwiper () {
                return this.list.length
            }
        }
    }
</script>

<style lang="stylus" scoped>
    .wrapper >>> .swiper-pagination-bullet-active
        background: #fff
    .wrapper
        width: 100%
        height: 0
        padding-bottom: 26.7%
        .swiper-img
          width: 100%
</style>
