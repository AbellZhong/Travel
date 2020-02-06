<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if='showSwiper'>
      <swiper-slide v-for='item of swiperList' v-bind:key='item.id'>
        <img class="swiper-img" v-bind:src="item.imgUrl"/>
    </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    swiperList: Array
  },
  data: function () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      }
    }
  },
  computed: {
    showSwiper () {
      return this.swiperList.length
    }
  }
}
</script>
<style lang='stylus' scoped>

.wrapper {
    width 100%
    height 0
    overflow hidden
    padding-bottom 31.25%
    background #eee
  .swiper-img {
    width: 100%;
  }
}
</style>
