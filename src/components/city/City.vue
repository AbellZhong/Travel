<template>
  <div>
  <CityHeader></CityHeader>
  <CitySearch></CitySearch>
  </div>
</template>

<script>
import CityHeader from './component/header'
import CitySearch from './component/search'
export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch
  }
}
</script>

<style scoped lang='stylus'>
@import '~styles/varibles.styl'
.search{
    height .72rem
    background $bgColor
    padding 0 .1rem
}
</style>
