<template>
    <div>
        <div class="banner" @click="handleClick">
            <img class="banner-img" :src="bannerImg"/>
            <div class="banner-info">
                <div class="banner-title">{{this.sightName}}</div>
                <div class="banner-icon">
                    <span class="iconfont">&#xe647;</span>
                    <em class="icon-number">{{this.gallaryImgs.length}}</em>
                </div>            
            </div>
        </div>
        <fade-animation>
            <common-gallary 
            :imgs="gallaryImgs" 
            v-show="showGallary"
            @close="handleGallaryClose">
            </common-gallary>
        </fade-animation>        
    </div>   
</template>

<script>
import CommonGallary from 'common/gallary/Gallary.vue'
import FadeAnimation from 'common/fadeAnimation/FadeAnimation.vue'
export default {
    name: 'DetailBanner',
    props: {
        sightName: String,
        bannerImg: String,
        gallaryImgs: Array
    },
    data () {
        return { 
            showGallary: false
        }
    },
    methods: {
        handleClick () {
             this.showGallary = true
        },
        handleGallaryClose () {
            this.showGallary = false
        }
    },
    components: {
        CommonGallary,
        FadeAnimation 
    }
}
</script>

<style lang="stylus" scoped>
     .banner 
         position: relative
         overflow: hidden
         width: 100%
         height: 0
         padding-bottom: 55%
     .banner-img 
         width: 100%
     .banner-info 
         position: absolute
         left: .2rem
         bottom: .36rem
         color: #fff
         .banner-title
            position: relative
            z-index: 1
            line-height: .4rem
            color: #fff
            font-size: .36rem
            text-shadow: 0 1px 2px rgba(0, 0, 0, 0.70)
        .banner-icon 
            position: absolute
            bottom: .5rem
            width: 1.2rem
            font-size: .24rem
            line-height: .4rem  
            text-align: center 
            border-radius: .2rem           
            background: rgba(0, 0 ,0, .5)
            .iconfont
                font-size: .2rem
        .banner::after 
            content: "\0020"
            display: block
            position: absolute
            bottom: 0
            left: 0
            width: 100%
            min-height: .6rem
            background-color: transparent
            background-image: linear-gradient(to bottom, rgba(0, 0, 0, 0), rgba(0, 0, 0, .8))        
</style>