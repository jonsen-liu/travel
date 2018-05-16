<template>
  <div class="father-swiper">
    <swiper :options="swiperOption">
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
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [
        {
          id: '0001',
          imgUrl: '@/assets/imgs/baner99y.jpg',
          url: 'http://img1.qunarzz.com/piao/fusion/1804/f2/91b285a08ee21c02.jpg_750x200_8a73fd08.jpg'
        }, {
          id: '0002',
          imgUrl: '@/assets/imgs/banerdxh.jpg',
          url: 'http://img1.qunarzz.com/piao/fusion/1805/10/3ee6df72beb86402.jpg_750x200_e02a4c99.jpg'
        }, {
          id: '0003',
          imgUrl: '@/assets/imgs/banergay.jpg',
          url: 'http://img1.qunarzz.com/piao/fusion/1804/3e/4d6e12949f74fc02.jpg_750x200_22aba1bb.jpg'
        }, {
          id: '0004',
          imgUrl: '@/assets/imgs/banerglx.jpg',
          url: 'http://img1.qunarzz.com/piao/fusion/1805/ab/0364cd7b56f95702.jpg_750x200_ccb27048.jpg'
        }, {
          id: '0005',
          imgUrl: '@/assets/imgs/banerjlz.jpg',
          url: 'http://img1.qunarzz.com/piao/fusion/1805/e8/14b75b1c81fbe702.jpg_750x200_e6d4f1f1.jpg'
        }
      ]
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
