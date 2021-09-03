<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-content">
            <img class="icon-img" :src="item.imgUrl" />
            <div class="keyword">{{ item.keyword }}</div>
          </div>
        </div>
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: "HomeIcons",
  props: {
    list: Array
  },
  data() {
    return {
      swiperOption: {
        pagination: ".swiper-pagination",
        autoplay: false,
        observer: true, //修改swiper自己或子元素时，自动初始化swiper
        observeParents: true //修改swiper的父元素时，自动初始化swiper
      }
    };
  },
  computed: {
    pages() {
      const pages = [];
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8);
        if (!pages[page]) {
          pages[page] = [];
        }
        pages[page].push(item);
      });
      return pages;
    }
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl'
@import '~styles/mixins.styl'
.icons >>> .swiper-pagination-bullet
    width: .12rem
    height: .12rem
    background: rgba(0,175,190,.8)
.icons >>> .swiper-container-horizontal > .swiper-pagination-bullets
    bottom: .1rem
.icons >>> .swiper-container
    overflow: hidden
    height: 3.7rem
    padding-top: .1rem
    background-color: #fff
    .icon
        position: relative
        float: left
        width: 25%
        height: 1.5rem
        padding-top : .1rem
        color: $darkColor
        text-align: center
        .icon-content
            position: absolute
            top: .10rem
            left: 0
            right: 0
            bottom: .44rem
            padding: .1rem
            .icon-img
                width: 1.1rem
                height: 1.1rem
            .keyword
                margin-top: .1rem
                ellipsis()
</style>
