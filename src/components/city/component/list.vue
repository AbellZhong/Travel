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
            <div class="button-wrapper">
                <div class="button">杭州</div>
            </div>
             <div class="button-wrapper">
                <div class="button">成都</div>
            </div>
             <div class="button-wrapper">
                <div class="button">武汉</div>
            </div>
             <div class="button-wrapper">
                <div class="button">重庆</div>
            </div>
             <div class="button-wrapper">
                <div class="button">北京</div>
            </div>
             <div class="button-wrapper">
                <div class="button">上海</div>
            </div>
             <div class="button-wrapper">
                <div class="button">广州</div>
            </div>
             <div class="button-wrapper">
                <div class="button">深圳</div>
            </div>
        </div>
    </div>
    <div class="area">
        <div class="title border-topbottom">A</div>
        <div class="item-list">
            <div class="item border-bottom">阿拉善</div>
            <div class="item border-bottom">阿拉尔</div>
            <div class="item border-bottom">阿拉善</div>
            <div class="item border-bottom">阿拉善</div>
            <div class="item border-bottom">阿拉善</div>
        </div>
    </div>
    <div class="area">
        <div class="title border-topbottom">B</div>
        <div class="item-list">
            <div class="item border-bottom">阿拉善</div>
            <div class="item border-bottom">阿拉尔</div>
            <div class="item border-bottom">阿拉善</div>
            <div class="item border-bottom">阿拉善</div>
            <div class="item border-bottom">阿拉善</div>
        </div>
    </div>
    <div class="area">
        <div class="title border-topbottom">C</div>
        <div class="item-list">
            <div class="item border-bottom">阿拉善</div>
            <div class="item border-bottom">阿拉尔</div>
            <div class="item border-bottom">阿拉善</div>
            <div class="item border-bottom">阿拉善</div>
            <div class="item border-bottom">阿拉善</div>
        </div>
    </div>
    <div class="area">
        <div class="title border-topbottom">D</div>
        <div class="item-list">
            <div class="item border-bottom">阿拉善</div>
            <div class="item border-bottom">阿拉尔</div>
            <div class="item border-bottom">阿拉善</div>
            <div class="item border-bottom">阿拉善</div>
            <div class="item border-bottom">阿拉善</div>
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
