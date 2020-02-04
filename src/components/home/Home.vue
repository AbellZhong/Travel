<template>
<div>
  <HomeHeader></HomeHeader>
  <HomeSwiper></HomeSwiper>
  <HomeIcons></HomeIcons>
  <HomeRecommend></HomeRecommend>
  <HomeWeekend></HomeWeekend>
</div>
</template>

<script>
import HomeHeader from './comoponent/header'
import HomeSwiper from './comoponent/swiper'
import HomeIcons from './comoponent/icons'
import HomeRecommend from './comoponent/recommend'
import HomeWeekend from './comoponent/weekend'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  }
}
</script>

<style>

</style>
