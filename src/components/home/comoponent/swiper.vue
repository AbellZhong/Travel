<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
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
  data: function () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20201/be6871c9b0b0ffab3ef2a86fa9688677.jpg'
      }, {
        id: '0002',
        imgUrl: 'https://pic.c-ctrip.com/flight/fdo/flight-index/baozhang-shengji.jpg'
      }, {
        id: '0003',
        imgUrl: 'https://dimg04.c-ctrip.com/images/zg041c000001dsz2wD2AC.jpg'
      }, {
        id: '0004',
        imgUrl: 'https://dimg04.c-ctrip.com/images/zg0e1a0000019t45c6EB7.jpg'
      }]
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
