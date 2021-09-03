<template>
    <div>
        <router-link tag="div" to="/" class="header-abs" v-show="showAbs">
             <span class="iconfont header-abs-back">&#xe624;</span>
        </router-link>
        <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
            <router-link to="/">
                <div class="iconfont header-back">&#xe624;</div>  
            </router-link>
            <h1 class="header-title">南沙湿地公园</h1>
        </div>
    </div>   
</template>

<script>
export default {
    name: 'DetailHeader',
    data () {
        return {
            showAbs: true,
            opacityStyle: {
                opacity: 0
            }
        }       
    },
    methods: {
        handleScroll () {
            const top = document.documentElement.scrollTop || window.pageYOffset || document.body.scrollTop
            if (top > 40) {
                let opacity = top / 206
                opacity = opacity > 1 ? 1 : opacity
                this.opacityStyle = { opacity: opacity }
                this.showAbs = false
            }
            else {
                this.showAbs = true
            }
        }  
    },
    created () {
        window.addEventListener('scroll', this.handleScroll)
    },
    deactivated () {
        window.removeEventListener('scroll', this.handleScroll)
    }
}
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl'
     .header-abs
         position: absolute 
         top: .1rem
         left: .1rem
         width: .72rem
         height: .72rem
         line-height: .72rem
         text-align: center  
         border-radius: .36rem
         background: rgba(0, 0, 0, .5)
         .header-abs-back
             color: #fff
    .header-fixed
        position: fixed
        z-index: 90
        top: 0
        left: 0
        right: 0
        height: .88rem
        background: $bgColor
        color: #fff 
        .header-back
            position: absolute
            left: 0
            top: 0
            width: .8rem
            font-size: .36rem
            text-align: center
            line-height: .88rem 
            color: #fff            
        .header-title
            margin: 0 1rem
            font-size: .32rem
            line-height: .88rem
            text-align: center     
</style>