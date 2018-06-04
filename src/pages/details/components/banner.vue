<template>
  <div>
    <div class="banner" @click="bannerClick">
      <img :src="bannerImg">
      <div class="banner-title">
        <div class="banner-icone">
          <span class="iconfont">&#xe605;</span>
          {{this.gallaryImgs.length}}
        </div>
        {{this.sightName}}
      </div>
    </div>
    <common-gallery v-show="galleryShow" @galleryclick="galleryClick" :imgs="gallaryImgs"></common-gallery>
  </div>
</template>

<script>
// import { mapState } from 'vuex'
import commonGallery from 'common/gallery/Gallery'
export default {
  name: 'detailBanner',
  components: {
    commonGallery
  },
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
  },
  data () {
    return {
      galleryShow: false,
      imgs: []
    }
  },
  methods: {
    bannerClick () {
      this.galleryShow = true
    },
    galleryClick () {
      this.galleryShow = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .banner
    overflow hidden
    height 0
    padding-bottom 55%
    position relative
    img
      width 100%
    .banner-title
      position absolute
      left 0
      right 0
      bottom 0
      color #fff
      height 1.2rem
      font-size .36rem
      padding-left .2rem
      background-image linear-gradient(rgba(0,0,0,0),rgba(0,0,0,.12),rgba(0,0,0,.3),rgba(0,0,0,.8))
      .banner-icone
        width 1.2rem
        height 0.4rem
        line-height .4rem
        font-size .2rem
        text-align center
        margin 0 0 .1rem
        background-color rgba(0, 0, 0, .6)
        border-radius .18rem
        .iconfont
          font-size .16rem
</style>
