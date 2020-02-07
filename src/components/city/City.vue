<template>
  <div>
  <CityHeader></CityHeader>
  <CitySearch></CitySearch>
  <CityList></CityList>
  <CityAlphabet></CityAlphabet>
  </div>
</template>

<script>
import CityHeader from './component/header'
import CitySearch from './component/search'
import CityList from './component/list'
import CityAlphabet from './component/alphabet'
export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  }
}
</script>

<style scoped lang='stylus'>
</style>
