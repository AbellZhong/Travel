<template>
<div>
  <HomeHeader></HomeHeader>
  <HomeSwiper></HomeSwiper>
</div>
</template>

<script>
import HomeHeader from './comoponent/header'
import HomeSwiper from './comoponent/swiper'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper
  }
}
</script>

<style>

</style>
