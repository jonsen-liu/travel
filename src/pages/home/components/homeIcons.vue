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
  props: {
    iconList: Array
  },
  data: function () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination'
      }
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
