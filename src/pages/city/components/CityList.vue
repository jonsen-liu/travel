<template>
  <div class="city-list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">{{this.citylist}}</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper"
          v-for="item of hotcities"
          :key="item.id"
          @click="hotCityClick(item.name)">
            <div class="button" v-text="item.name"></div>
          </div>
        </div>
      </div>
      <div class="area" v-for="(item, key) of cities"
      :key="key"
      :ref="key">
        <div class="title border-topbottom" v-text="key"></div>
        <div class="item-list">
          <div class="item border-bottom"
          v-for="inneritem of item"
          :key="inneritem.id"
          v-text="inneritem.name"
          @click="hotCityClick(inneritem.name)"></div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Bscroll from 'better-scroll'
import { mapState, mapMutations } from 'vuex'
export default {
  name: 'CityHeader',
  props: {
    cities: Object,
    hotcities: Array,
    letter: String
  },
  computed: {
    ...mapState({
      citylist: 'city'
    })
  },
  methods: {
    hotCityClick (city) {
      // this.$store.dispatch('changeCity', city)
      // this.$store.commit('changeCity', city)
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  watch: {
    letter () {
      if (this.letter) {
        let element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.border-topbottom
  &:before
    border-color #777
  &:after
    border-color #777
.border-bottom
  &:before
    border-color #777
.city-list
  overflow hidden
  position absolute
  top 1.54rem
  left 0
  right 0
  bottom 0
  .title
    line-height .54rem
    background-color #eee
    padding-left .2rem
    color #666
    font-size .26rem
  .button-list
    overflow hidden
    padding .1rem .6rem .1rem .1rem
    .button-wrapper
      float left
      width 33.33%
      .button
        padding .1rem 0
        text-align center
        margin .1rem
        border .02rem solid #ccc
        border-radius .06rem
  .item-list
    .item
      line-height .56rem
      color #666666
      padding-left .2rem

</style>
