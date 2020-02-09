<template>
  <div>
    <DetailBanner :sightName='sightName' :bannerImg='bannerImg' :gallaryImgs='gallaryImgs'></DetailBanner>
    <DetailHeader ></DetailHeader>
    <div class="content">
      <DetailList :categoryList='categoryList'></DetailList>
    </div>
  </div>
</template>

<script>
import DetailBanner from './component/banner'
import DetailHeader from './component/header'
import DetailList from './component/list'
import axios from 'axios'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      sightName: '',
      bannerImg: '',
      gallaryImgs: [],
      categoryList: []
    }
  },
  mounted () {
    this.getDetailInfo()
  },
  methods: {
    getDetailInfo () {
      axios.get('/api/detail.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(this.handleGetDataSucc)
    },
    handleGetDataSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.gallaryImgs = data.gallaryImgs
        this.categoryList = data.categoryList
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
.content{
  height 50rem
}
</style>
