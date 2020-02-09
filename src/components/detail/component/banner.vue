<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img :src="bannerImg" alt="" class="banner-img">
      <div class="banner-info">
        <div class="banner-title">{{this.sightName}}</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe674;</span>{{this.gallaryImgs.length}}
        </div>
      </div>
    </div>
    <common-gallary :imgs='gallaryImgs' v-show="showGallary" @close='handleGallaryClose'></common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallary
  },
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
