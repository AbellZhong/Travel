<template>
  <div>
  <CityHeader></CityHeader>
  <CitySearch></CitySearch>
  <CityList :cities='cities' :hotCities='hotCities'></CityList>
  <CityAlphabet :cities='cities'></CityAlphabet>
  </div>
</template>

<script>
import CityHeader from './component/header'
import CitySearch from './component/search'
import CityList from './component/list'
import CityAlphabet from './component/alphabet'
import axios from 'axios'
export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  mounted () {
    this.getCityInfo()
  },
  data () {
    return {
      cities: {},
      hotCities: []
    }
  },
  methods: {
    getCityInfo () {
      axios.get('/api/city.json').then(this.handleCityInfo)
    },
    handleCityInfo (res) {
      res = res.data
      if (res.ret && res.data) {
        this.cities = res.data.cities
        this.hotCities = res.data.hotCities
      }
    }
  }
}
</script>

<style scoped lang='stylus'>
</style>
