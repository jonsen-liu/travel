<template>
  <div class="banner">
    <img src="https://img1.qunarzz.com/sight/p0/1707/ab/abb70c851caaa6d8a3.img.jpg_600x330_af719163.jpg">
  </div>
</template>

<script>
// import { mapState } from 'vuex'
export default {
  name: 'detailBanner'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .banner
    overflow hidden
    height 0
    padding-bottom 55%
    img
      width 100%
</style>
