<template>
  <div class="home-icons">
    <swiper :options="swiperOption">
        <swiper-slide v-for="(swiperitem, index) of pages" :key="index">
          <div class="icon" v-for="item of swiperitem" :key="item.id">
            <div>
              <img :src="item.imgUrl">
            </div>
            <p class="icon-text" v-text="item.name"></p>
          </div>
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
  </div>
</template>

<script>
export default {
  name: 'homeIcons',
  data: function () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination'
      },
      iconList: [
        {
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          name: '景点门票',
          id: '0001'
        },
        {
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
          name: '必游榜单',
          id: '0002'
        },
        {
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
          name: '动物植物',
          id: '0003'
        },
        {
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/54/35899492b1302802.png',
          name: '公元',
          id: '0004'
        },
        {
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/89/55083b0f1951f302.png',
          name: '游船游艇',
          id: '0005'
        },
        {
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/bd/9f7b9b2b60c1502.png',
          name: '踏青赏花',
          id: '0006'
        },
        {
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
          name: '名胜古迹',
          id: '0007'
        },
        {
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
          name: '一日游',
          id: '0008'
        },
        {
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/b1/528a9e80403b8c02.png',
          name: '玩转长隆',
          id: '0009'
        },
        {
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/80/416c6ab3368d1f02.png',
          name: '全部玩乐',
          id: '0010'
        }
      ]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        !pages[page] && (pages[page] = [])
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang='stylus' scoped>
@import '~styles/varibles.styl'
@import '~styles/mixins.styl'
.swiper-pagination{
  position relative
  bottom 0
}
.home-icons {
  overflow: hidden
  width: 100%
  height: 3.6rem
  background-color $bgColorWhite
  box-sizing border-box
  .icon {
    float left
    width 25%
    height 50%;
    text-align center

    div {
      padding-top 0.15rem
      box-sizing border-box
      img {
        width 1.1rem
      }
    }
    .icon-text {
      line-height 0.3rem
      color $textColor
      ellipsis()
    }
  }
}
</style>
