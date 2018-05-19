<template>
  <div class="home">
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icons></home-icons>
    <home-hot></home-hot>
    <home-you-like></home-you-like>
    <home-weekend></home-weekend>
  </div>
</template>

<script>
import homeHeader from './components/header'
import homeSwiper from './components/swiper'
import homeIcons from './components/homeIcons'
import homeHot from './components/hot'
import homeYouLike from './components/youLike'
import homeWeekend from './components/weekend'
export default {
  name: 'Home',
  components: {
    homeHeader,
    homeSwiper,
    homeIcons,
    homeHot,
    homeYouLike,
    homeWeekend
  }
}
</script>

<style lang='stylus' scoped>
</style>
