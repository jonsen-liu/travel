<template>
  <div class="gallery" @click="galleryClick">
    <div class="gallery-center">
      <swiper :options="swiperOptions">
        <swiper-slide v-for="(item,index) of imgs" :key="index">
          <img class="gallery-img" :src="item">
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: 'commonGallery',
  props: {
    imgs: {
      type: Array
    }
  },
  data () {
    return {
      swiperOptions: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observer: true,
        observeParents: true
      }
    }
  },
  methods: {
    galleryClick () {
      this.$emit('galleryclick')
    }
  }
}
</script>

<style lang="stylus" scoped>
  .gallery-center >>> .swiper-container
    overflow visible
  .swiper-pagination
    color #fff
    bottom -1rem
  .gallery
    display flex
    flex-flow column
    justify-content center
    position absolute
    z-index 99
    top 0
    right 0
    left 0
    bottom 0
    background-color #000
    .gallery-center
      width 100%
      .gallery-img
        width 100%
</style>
