<template>
  <div class="details-header">
    <router-link tag="div" to="/" v-show="isShow" class="details-header-back">
      <div class="iconfont icon-back">&#xe624;</div>
    </router-link>
    <div class="header" v-show="!isShow" :style="opacityStyle">
      <router-link to="/">
        <div class="iconfont header-back">&#xe624;</div>
      </router-link>
      水上长隆乐园
    </div>
  </div>
</template>

<script>
export default {
  name: 'detailsHeader',
  data () {
    return {
      isShow: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    scrollTop () {
      let top = document.documentElement.scrollTop
      if (top > 50) {
        this.isShow = false
        let opacity = top / 160
        opacity = top / 160 > 1 ? 1 : opacity
        this.opacityStyle = {
          opacity
        }
      } else {
        this.isShow = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.scrollTop)
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.details-header-back
  position absolute
  top .16rem
  left .16rem
  width .8rem
  height .8rem
  line-height .8rem
  text-align center
  border-radius 50%
  background-color rgba(0, 0, 0, .6)
  .icon-back
    color #fff
.header
  position fixed
  top 0
  width 100%
  height .86rem
  line-height .86rem
  background $bgColor
  color #fff
  text-align center
  font-size .32rem
  .header-back
    position absolute
    width 1rem
    text-align center
    color #fff
</style>
