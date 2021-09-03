<template>
   <div>
        <div class="ticket-group" v-for="(item, index) of list" :key="index">
            <h3 class="ticket-type border-bottom">
                <span class="ticket-icon"></span>
                {{item.title}}
            </h3>
            <h3 v-if="item.children">
                <detail-list :list="item.children"></detail-list> 
            </h3>
            <div class="ticker-list">
                <div class="ticket-type-info border-bottom">
                    <h5 class="ticket-type-name">南沙湿地公园成人票</h5>
                    <div class="ticket-type-price">
                        ¥<em class="price-num">38</em>
                        <span class="price-numword">起</span>
                    </div>
                    <div class="ticket-type-extend iconfont">&#xe62d;</div>
                </div>
            </div>   
            <div class="ticker-list">
                <div class="ticket-type-info border-bottom">
                    <h5 class="ticket-type-name">南沙湿地公园成人票</h5>
                    <div class="ticket-type-price">
                        ¥<em class="price-num">38</em>
                        <span class="price-numword">起</span>
                    </div>
                    <div class="ticket-type-extend iconfont">&#xe62d;</div>
                </div>
            </div> 
            <div class="ticker-list">
                <div class="ticket-type-info border-bottom">
                    <h5 class="ticket-type-name">南沙湿地公园成人票</h5>
                    <div class="ticket-type-price">
                        ¥<em class="price-num">38</em>
                        <span class="price-numword">起</span>
                    </div>
                    <div class="ticket-type-extend iconfont">&#xe62d;</div>
                </div>
            </div>      
        </div> 
   </div>      
</template>

<script>
export default {
    name: 'DetailList',
    props: {
        list: Array
    }
}
</script>

<style lang="stylus" scoped>
    .ticket-group
        position: relative
        margin-bottom: .2rem
        .ticket-type 
            overflow: hidden
            height: .88rem
            position: relative
            margin-bottom: -.02rem
            font-size: .32rem
            line-height: .88rem
            padding: 0 .2rem
            background: #fff
            color: #333
            text-indent: .4rem
            .ticket-icon
               display: inline-block
               position: absolute
               width: .36rem
               height: .36rem
               top: .26rem
               left: .2rem
               background: url('http://s.qunarzz.com/piao/image/touch/sight/detail.png') 0 -.45rem no-repeat
               margin-right: .1rem
               background-size: .4rem 3rem
        .ticket-list
              overflow: hidden  
            .ticket-type-info
                position: relative
                margin-bottom: -.02rem
                padding: .24rem .2rem
                background:#fff 
            .ticket-type-price, .ticket-type-extend  
                 overflow: hidden
                 position: absolute
                 top: 50%
                 height: .4rem 
                 line-height: .4rem   
            .ticket-type-price       
                 right: .46rem
                 font-size: .24rem                 
                 margin-top: -.28rem
                 color: #ff9800  
                 .price-num
                     margin-left: .04rem
                     font-size: .4rem  
                  .price-numword
                     display: inline-block
                     color: #9e9e9e
                     font-size: .24rem 
            .ticket-type-extend
                right: .2rem
                margin-top: -.22rem
                color: #bbb
                font-size: .24rem                   
        .border-bottom::before
            border-bottom: 1px solid #e0e0e0     
            left: .2rem       
</style>