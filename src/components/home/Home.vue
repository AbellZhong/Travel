<template>
<div>
  <HomeHeader></HomeHeader>
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
import { mapState } from 'vuex'
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
      lastCity: '',
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    }
  },
  computed: {
    ...mapState(['city'])
  },
  mounted () {
    this.getHomeInfo()
    this.lastCity = this.city
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json?city=' + this.city).then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        this.swiperList = res.data.swiperList
        this.iconList = res.data.iconList
        this.recommendList = res.data.recommendList
        this.weekendList = res.data.weekendList
      }
    }
  },
  activated () {
    if (this.lastCity !== this.city) {
      this.lastCity = this.city
      this.getHomeInfo()
    }
  }
}
</script>

<style>

</style>
