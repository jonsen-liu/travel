<template>
  <div class="city-header">
    <router-link to="/">
      <div class="iconfont header-back">&#xe624;</div>
    </router-link>
    城市选择
  </div>
</template>
<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.city-header
  position relative
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
