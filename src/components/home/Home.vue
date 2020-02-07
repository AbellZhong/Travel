<template>
<div>
  <HomeHeader :city='city'></HomeHeader>
  <HomeSwiper :swiperList='swiperList'></HomeSwiper>
  <HomeIcons :iconList='iconList'></HomeIcons>
  <HomeRecommend :recommendList='recommendList'></HomeRecommend>
  <HomeWeekend :weekendList='weekendList'></HomeWeekend>
</div>
</template>

<script>
import HomeHeader from './component/header'
import HomeSwiper from './component/swiper'
import HomeIcons from './component/icons'
import HomeRecommend from './component/recommend'
import HomeWeekend from './component/weekend'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  data () {
    return {
      city: '',
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    }
  },
  mounted () {
    this.getHomeInfo()
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json').then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        this.city = res.data.city
        this.swiperList = res.data.swiperList
        this.iconList = res.data.iconList
        this.recommendList = res.data.recommendList
        this.weekendList = res.data.weekendList
      }
    }
  }
}
</script>

<style>

</style>
