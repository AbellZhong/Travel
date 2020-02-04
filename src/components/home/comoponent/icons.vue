<template>
  <div class="icons">
    <swiper>
      <swiper-slide v-for="(page,index) of pages" :key='index'>
        <div class="icon" v-for="item of page" v-bind:key="item.id">
          <div class="icon-img">
            <img v-bind:src="item.imgUrl" alt class="icon-img-content" />
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcon',
  data: function () {
    return {
      iconList: [
        {
          id: '0001',
          imgUrl:
            'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          desc: '景点门票'
        },
        {
          id: '0002',
          imgUrl:
            'https://imgs.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
          desc: '名胜古迹'
        },
        {
          id: '0003',
          imgUrl:
            'https://imgs.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
          desc: '绍兴必游'
        },
        {
          id: '0004',
          imgUrl:
            'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/a40ee278d67000f2a29d2e20f6a029b3.png',
          desc: '自然风光'
        },
        {
          id: '0005',
          imgUrl:
            'https://imgs.qunarzz.com/piao/fusion/1803/67/9a1678221b8e0e02.png',
          desc: '古镇'
        },
        {
          id: '0006',
          imgUrl:
            'https://imgs.qunarzz.com/piao/fusion/1803/fc/b10a6b2e4f0fe102.png',
          desc: '乔波冰雪'
        },
        {
          id: '0007',
          imgUrl:
            'https://imgs.qunarzz.com/piao/fusion/1803/b8/c5dcdb58deec2402.png',
          desc: '柯岩'
        },
        {
          id: '0008',
          imgUrl:
            'https://imgs.qunarzz.com/piao/fusion/1803/c1/6f15f887179fa002.png',
          desc: '新昌大佛寺'
        },
        {
          id: '0009',
          imgUrl:
            'https://imgs.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png',
          desc: '泡温泉'
        }
      ]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang='stylus' scoped>
@import '~styles/varibles.styl';
@import '~styles/mixins.styl';
.icons >>> .swiper-container {
  overflow: hidden;
  height: 0;
  padding-bottom: 50%;
}

.icons {
  height: 0;
  padding-bottom: 50%;
  overflow: hidden;

  .icon {
    position: relative;
    overflow: hidden;
    width: 25%;
    float: left;
    padding-bottom: 25%;
    height: 0;

    .icon-img {
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0.44rem;
      box-sizing: border-box;
      padding: 0.1rem;

      .icon-img-content {
        height: 100%;
        display: block;
        margin: 0 auto;
      }
    }

    .icon-desc {
      position: absolute;
      left: 0;
      right: 0;
      bottom: 0;
      line-height: 0.44rem;
      height: 0.44rem;
      color: $darkTextColor;
      text-align: center;
      ellipsis()
    }
  }
}
</style>
