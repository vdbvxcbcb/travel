<template>
<div class="group">
    <div>
        <h2 class="weekend-title">周末去哪儿</h2>
    </div>
    <ul class="item">
        <li class="border-bottom" v-for="item of list" :key="item.id">
            <div class="item-imgcontainer">
                <img class="item-img" :src="item.imgUrl"/>
            </div>
            <div class="item-info">
                 <p class="item-name">{{item.title}}</p>
                 <p class="item-desc">{{item.desc}}</p>
            </div>
        </li>
    </ul>
</div>  
</template>

<script>
    export default {
        name: 'HomeWeekend',
        props: {
            list: Array
        }
    }
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
        .weekend-title
            height: .8rem
            padding-left: .26rem
            line-height : .8rem
            color: #212121
        .item
            background: #fff     
            .item-imgcontainer
                height: 0
                padding-bottom: 37.435%
                overflow: hidden                
                .item-img
                    width: 100%
            .item-info
                padding: .14rem .2rem .2rem .2rem        
                .item-name
                    padding-right: 1.4rem
                    color: #212121
                    font-size: .28rem
                    line-height: .48rem
                    ellipsis()
                .item-desc
                    padding-right: 1.4rem
                    color: #616161
                    font-size: .24rem
                    line-height: .42rem;
                    ellipsis()                 
</style>