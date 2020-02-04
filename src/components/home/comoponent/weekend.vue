<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <div class="item-img-wrapper">
          <img :src="item.imgUrl" alt class="item-img" />
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      recommendList: [
        {
          id: '0001',
          imgUrl:
            'https://imgs.qunarzz.com/sight/source/1606/18/fccb1a2f45f742.jpg_r_640x214_55564c3f.jpg',
          title: '美丽普陀山',
          desc:
            '人间仙境杭州，佛教圣地普陀山等你来玩！在这里静心接收佛家的洗礼，用心感受佛文化'
        },
        {
          id: '0002',
          imgUrl:
            'https://imgs.qunarzz.com/sight/source/1811/52/b6776b49d27025.jpg_r_640x214_35ae205c.jpg',
          title: '绍兴古居畅游',
          desc:
            '这里是一代文豪诞生地，也是现今的文化历史街区，感受浓厚的历史人文沉淀'
        },
        {
          id: '0003',
          imgUrl:
            'https://imgs.qunarzz.com/sight/source/1510/c1/afe3ab32b3bc23.jpg_r_640x214_beb61760.jpg',
          title: '绍兴必打卡',
          desc: '打卡绍兴必玩景点，感受人杰地灵的绍兴风华'
        },
        {
          id: '0004',
          imgUrl:
            'https://imgs.qunarzz.com/sight/source/1810/17/30354793b9f72e.jpg_r_640x214_8df352c4.jpg',
          title: '精致暖汤',
          desc:
            '天然高品质温泉，这是冬天秀美容颜首选之地，让你疲惫的身影在这里消失的无影无踪'
        },
        {
          id: '0005',
          imgUrl:
            'https://imgs.qunarzz.com/sight/source/1606/18/fccb1a2f45f742.jpg_r_640x214_55564c3f.jpg',
          title: '亲子时光必玩',
          desc:
            '这个周末别宅在家里了，带宝贝走进大自然或去主题乐园打卡吧，呼吸清新空气回归自然'
        }
      ]
    }
  }
}
</script>

<style scoped lang='stylus'>
@import '~styles/mixins.styl';

.title {
  line-height: 0.8rem;
  background: #eee;
  text-indent: 0.2rem;
  margin-top: 0.2rem;
}

.item-img-wrapper {
  height: 0;
  overflow: hidden;
  padding-bottom: 33.9%;
}

.item-img {
  width: 100%;
}

.item-info {
  padding: 0.1rem;
  .item-title {
    line-height: 0.54rem;
    font-size: 0.32rem;
    ellipsis();
  }

  .item-desc {
    line-height: 0.4rem;
    color: #ccc;
    ellipsis();
  }
}
</style>
