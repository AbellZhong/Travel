<template>
  <div>
    <div class="recommend-title">热销推荐</div>
      <ul>
        <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
          <img :src="item.imgUrl" alt class="item-img" />
          <div class="item-info">
            <p class="item-title">{{item.title}}</p>
            <p class="item-desc">{{item.desc}}</p>
            <button class="item-btn">查看详情</button>
          </div>
        </li>
      </ul>
    </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [
        {
          id: '0001',
          imgUrl:
            'https://imgs.qunarzz.com/sight/p0/1801/5d/5d24bb249f8ca889a3.water.jpg_200x200_77551cb9.jpg',
          title: '澳门脱衣舞演出',
          desc: '将壮观诠释到完美,将梦想展示给世界'
        },
        {
          id: '0002',
          imgUrl:
            'https://imgs.qunarzz.com/sight/p0/1903/b0/b0a81289b537c934a3.water.jpg_200x200_816c0f59.jpg',
          title: '澳门蹦极塔',
          desc: '将壮观诠释到完美,将梦想展示给世界'
        },
        {
          id: '0003',
          imgUrl:
            'https://imgs.qunarzz.com/sight/p0/1501/18/181cff1e8af11041.water.jpg_200x200_2e185c41.jpg',
          title: '维多利亚海港',
          desc: '将壮观诠释到完美,将梦想展示给世界'
        },
        {
          id: '0004',
          imgUrl:
            'https://imgs.qunarzz.com/sight/p0/1705/c2/c2249cf7d5ae5b71a3.img.jpg_200x200_a45459dc.jpg',
          title: '澳门巴黎皇家赌场',
          desc: '将壮观诠释到完美,将梦想展示给世界'
        },
        {
          id: '0005',
          imgUrl:
            'https://imgs.qunarzz.com/sight/p0/1501/df/dfd428066cc4a607.water.jpg_200x200_f41c6cfc.jpg',
          title: '香港美杜莎夫人蜡像馆',
          desc: '将壮观诠释到完美,将梦想展示给世界'
        }
      ]
    }
  }
}
</script>

<style scoped lang='stylus'>
@import '~styles/mixins.styl';

.recommend-title {
  line-height: 0.8rem;
  background: #eee;
  text-indent: 0.2rem;
  margin-top: 0.2rem;
}

.item {
  overflow: hidden;
  display: flex;
  height: 1.9rem;

  .item-img {
    width: 1.7rem;
    height: 1.7rem;
    padding: 0.1rem;
  }

  .item-info {
    flex: 1;
    padding: 0.1rem;
    min-width: 0;

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

    .item-btn {
      background: grey;
      padding: 0 0.2rem;
      border-radius: 0.06rem;
      color: #fff;
      line-height: 0.44rem;
    }
  }
}
</style>
