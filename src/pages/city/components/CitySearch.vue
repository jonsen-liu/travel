<template>
  <div>
    <div class="city-search">
      <input type="text" v-model="keydata" placeholder="输入城市或拼音搜素">
    </div>
    <div class="search-content" ref="search" v-show="keydata">
      <ul>
        <li class="search-list border-bottom" v-for="item of list" :key="item.id">{{item.name}}</li>
        <li class="search-list border-bottom" v-show="showHint">没有数据显示</li>
      </ul>
    </div>
  </div>
</template>
<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keydata: '',
      list: [],
      time: null
    }
  },
  computed: {
    showHint () {
      const showHint = !this.list.length
      return showHint
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  },
  watch: {
    keydata () {
      clearTimeout(this.time)
      if (!this.keydata) {
        this.list = []
        return
      }
      const result = []
      this.time = setTimeout(() => {
        for (let i in this.cities) {
          this.cities[i].forEach((v) => {
            if (v.spell.search(this.keydata) > -1 || v.name.search(this.keydata) > -1) {
              result.push(v)
            }
          })
        }
        this.list = result
      }, 100)
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';
.border-bottom
  &:before
    border-color #777
.city-search
  margin-top -.02rem
  background-color $bgColor
  padding 0 .1rem .1rem
  input
    width 100%
    height .6rem
    font-size .32rem
    text-align center
    border-radius .1rem
    padding 0 .2rem
    color #666
    box-sizing border-box
.search-content
  overflow hidden
  position absolute
  top 1.54rem
  left 0
  right 0
  bottom 0
  z-index 1
  background-color $homebgcolor
  .search-list
    padding-left .2rem
    line-height .56rem
    color #666666
</style>
