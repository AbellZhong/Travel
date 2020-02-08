<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img src="http://img1.qunarzz.com/sight/p0/1801/5d/5d24bb249f8ca889a3.water.jpg_600x330_378727c0.jpg" alt="" class="banner-img">
      <div class="banner-info">
        <div class="banner-title">澳门水舞间演出</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe674;</span>39
        </div>
      </div>
    </div>
    <common-gallary :imgs='imgs' v-show="showGallary" @close='handleGallaryClose'></common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallary
  },
  data () {
    return {
      showGallary: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1908/8a/8aa775e2f891ab44a3.img.jpg_r_800x800_ad0688d9.jpg', 'http://img1.qunarzz.com/sight/p0/201305/30/bcfc83ddc78550dcc8d65eac.jpg_r_800x800_37c6ff88.jpg']
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  }
}
</script>

<style lang="stylus" scoped>
.banner{
  overflow hidden
  height 0
  padding-bottom 55%
  position relative
  .banner-img{
    width 100%
  }
  .banner-info{
    position absolute
    left 0
    right 0
    bottom 0
    line-height .6rem
    display flex
    color #fff
    background-img linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
    .banner-title{
      flex 1
      font-size .32rem
      padding 0 .2rem
    }
    .banner-number{
      margin-top .14rem
      padding 0 .4rem
      line-height .32rem
      height .32rem
      border-radius .2rem
      background rgba(0,0,0,0.8)
      font-size .24rem
      .banner-icon{
        font-size .24rem
      }
    }
  }
}
</style>
