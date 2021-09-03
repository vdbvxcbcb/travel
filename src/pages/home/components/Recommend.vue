<template>
<div class="group">
    <div class="group-title">
        <img class="title-img" alt="猜你喜欢" src="http://img1.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png"/>
        <span class="title">猜你喜欢</span>
    </div>
    <ul>
        <router-link 
           tag="li" 
           class="item border-bottom" 
           v-for="item of list" 
           :key="item.id"
           :to="'/detail/' + item.id">
            <img class="item-img" :src="item.imgUrl"/>
            <div 
            class="item-tag" 
            style="background-image:url(https://img1.qunarzz.com/piao/fusion/1802/52/b9080e45b69b4f02.png)">
            可订明日
            </div>
            <div class="item-info">
                 <p class="item-title">{{item.title}}</p>
                 <div class="item-comment">
                     <span class="starLevel">
                         <strong class="iconfont starLevel-total">&#xe613;&#xe613;&#xe613;&#xe613;&#xe613;</strong>
                     </span>
                     <span class="comment-num">13016条评论</span>
                 </div>
                 <div class="item-price">
                       <span class="price"> 
                           ¥<em class="price-num">88</em>
                       </span>
                        起
                       <span class="address">番禺区</span>
                 </div>
                 <div class="item-detail">
                       <p class="item-desc">{{item.desc}}</p>                           
                       <button class="item-button">查看详情</button> 
                 </div>                
            </div>
        </router-link>
    </ul>
</div>  
</template>

<script>
    export default {
        name: 'HomeRecommend',
        props: {
            list: Array
        }
    }
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
    .group
        margin-top: .2rem
        background: #fff
        .group-title
            padding: .24rem 0 .26rem
            font-size: .24rem
            .title-img
                width: .3rem
                height: .3rem
                margin-left: .2rem
                overflow: hidden
                vertical-align: top
            .title
                display: inline-block
                color: #212121
                margin-left: .08rem
                font-size: .32rem
                line-height: .44rem              
        .item
            position: relative 
            display: flex
            padding: .2rem 0
            margin-left: .24rem
            overflow: hidden   
            .item-img
                width: 2rem
                height: 2rem
            .item-tag               
                position: absolute
                top: .2rem
                left: 0
                width: 1.02rem
                height: .38rem
                background-size: 100% 
                color: #fff
                font-size: .2rem
                line-height: .38rem
                text-indent: .04rem                           
            .item-info
                flex: 1
                padding-left: .22rem
                min-width: 0
                .item-title
                    font-size: .32rem
                    line-height: .54rem
                    ellipsis()
                .item-comment
                    margin-top: .14rem
                    height: .34rem
                    .starLevel
                        display: inline-block
                        position: relative
                        width: 1.5rem
                        height: .28rem
                        letter-spacing: .02rem
                        transform: scale(.83)
                        -webkit-transform-origin: 0 0  
                        .starLevel-total
                             overflow: hidden
                             position: absolute
                             top: .04rem
                             left: 0
                             height: .28rem   
                             z-index: 1
                             color: #ffb436
                    .comment-num
                        color: #616161
                        font-size: .24rem
                        line-height: .34rem
                        vertical-align: text-bottom  
                .item-price
                    position: relative
                    margin-top: .22rem
                    color: #616161
                    font-size: .24rem
                    line-height: .4rem
                    .price
                        color: #ff8300   
                        .price-num
                            font-size: .4rem
                    .address
                        position: absolute
                        right: .24rem
                        bottom: 0    
                .item-detail
                    position: relative                    
                    .item-desc
                        display: inline-block
                        margin-top: .2rem
                        margin-right: .24rem
                        padding: .04rem .1rem
                        font-size: .24rem
                        line-height: .34rem
                        color: #f55  
                        background: #fff9f9
                        ellipsis()
                    .item-button
                        position: absolute
                        right: .24rem
                        bottom: .1rem
                        background: #ff9300
                        font-size: .24rem
                        line-height: .34rem
                        margin-top: .2rem
                        padding: .04rem .1rem
                        border-radius: .06rem
                        color: #fff 
        .border-bottom::before
            border-bottom: 1px solid #e0e0e0                  
</style>