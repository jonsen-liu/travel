<template>
  <div class="city-search">
    <input type="text" placeholder="输入城市或拼音搜素">
  </div>
</template>
<script>
export default {
  name: 'CitySearch'
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.city-search {
  margin-top -.02rem
  background-color $bgColor
  padding 0 .1rem .1rem
  input {
    width 100%
    height .6rem
    font-size .32rem
    text-align center
    border-radius .1rem
    padding 0 .2rem
    color #666
    box-sizing border-box
  }
}
</style>
