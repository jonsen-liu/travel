<template>
  <div class="home">
    <home-header></home-header>
    <home-swiper :swiperList="swiperList"></home-swiper>
    <home-icons :iconList="iconList"></home-icons>
    <home-hot :Hot="Hot"></home-hot>
    <home-you-like :youLike="youLike"></home-you-like>
    <home-weekend :weekendList="weekendList"></home-weekend>
  </div>
</template>

<script>
import homeHeader from './components/header'
import homeSwiper from './components/swiper'
import homeIcons from './components/homeIcons'
import homeHot from './components/hot'
import homeYouLike from './components/youLike'
import homeWeekend from './components/weekend'
import { mapState } from 'vuex'

import axios from 'axios'
export default {
  name: 'Home',
  components: {
    homeHeader,
    homeSwiper,
    homeIcons,
    homeHot,
    homeYouLike,
    homeWeekend
  },
  data () {
    return {
      lastCity: '',
      swiperList: [],
      iconList: [],
      Hot: [],
      youLike: [],
      weekendList: []
    }
  },
  computed: {
    ...mapState(['city'])
  },
  methods: {
    getHomeInfo () {
      axios.get('./api/index.json?city=' + this.city)
        .then(this.getHomeInfoSucc)
      this.lastCity = this.city
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.status) {
        var data = res.data
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.Hot = data.Hot
        this.youLike = data.youLike
        this.weekendList = data.weekendList
      }
    }
  },
  mounted () {
    this.getHomeInfo()
  },
  activated () {
    if (this.lastCity !== this.city) {
      // this.lastCity = this.city
      this.getHomeInfo()
    }
  }
}
</script>

<style lang='stylus' scoped>
@import '~styles/varibles.styl'
.home
  background-color $homebgcolor
</style>
