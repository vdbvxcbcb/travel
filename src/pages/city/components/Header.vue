<template>
    <div class="header">
        <router-link to="/">
            <div class="iconfont header-back">&#xe624;</div>  
        </router-link>
        <h1 class="header-title">城市选择</h1>
    </div>
</template>

<script>
export default {
    name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl'
    .header
        position: relative
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