<template>
<div>
  <HomeHeader></HomeHeader>
  <HomeSwiper></HomeSwiper>
  <HomeIcons></HomeIcons>
</div>
</template>

<script>
import HomeHeader from './comoponent/header'
import HomeSwiper from './comoponent/swiper'
import HomeIcons from './comoponent/icons'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons
  }
}
</script>

<style>

</style>
