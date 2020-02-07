<template>
  <div class="list" ref='wrapper'>
    <div>
    <div class="area">
        <div class="title border-topbottom">您的位置</div>
        <div class="button-list">
            <div class="button-wrapper">
                <div class="button">杭州</div>
            </div>
        </div>
    </div>
    <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
            <div class="button-wrapper" v-for="item of hotCities" :key='item.id'>
                <div class="button">{{item.name}}</div>
            </div>
        </div>
    </div>
    <div class="area" v-for='(item,key) of cities' :key='key' :ref="key">
        <div class="title border-topbottom">{{key}}</div>
        <div class="item-list">
            <div class="item border-bottom" v-for='innerItem of item' :key='innerItem.id'>{{innerItem.name}}</div>
        </div>
    </div>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'CityList',
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  },
  props: {
    cities: Object,
    hotCities: Array,
    letter: String
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  }
}
</script>

<style scoped lang='stylus'>
@import '~styles/varibles.styl'
.border-topbottom{
    &:before{
        border-color #ccc
    }
    &:after{
        border-color #ccc
    }
}
.border-bottom{
    &:before{
        border-color #ccc
    }
}
.list{
    overflow hidden
    position absolute
    top 1.58rem
    left 0
    right 0
    bottom 0
.title{
    line-height .54rem
    background #eeeeee
    padding-left .2rem
    font-size .26rem
    color #666
}
.button-list{
    overflow hidden
    padding .1rem .6rem .1rem .1rem
    .button-wrapper{
        width 33.33%
        float left
        .button{
            text-align center
            margin .1rem
            border .02rem solid #cccccc
            padding .1rem 0
            border-radius .06rem
        }
    }
}
.item-list{
    .item{
        line-height .76rem
        padding-left .2rem
    }
}
}
</style>
