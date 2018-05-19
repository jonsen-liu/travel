<template>
  <div class="father-swiper">
    <swiper :options="swiperOption" v-if="showList">
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.url">
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'homeSwiper',
  props: {
    swiperList: Array
  },
  data () {
    return {
      swiperOption: {
        autoplay: 1500,
        pagination: '.swiper-pagination',
        loop: true
      }
    }
  },
  computed: {
    showList () {
      return this.swiperList.length
    }
  }
}
</script>
<style lang='stylus' scoped>
  .father-swiper >>> .swiper-pagination-bullet-active{
    background #fff !important
  }
  .father-swiper{
    overflow hidden;
    width 100%;
    height 0
    padding-bottom 26.67%
    .swiper-img {
      width 100%
    }
  }

</style>
