<template>
  <div class="details">
    <detail-banner
    :sightName="sightName"
    :bannerImg="bannerImg"
    :gallaryImgs="gallaryImgs">
    </detail-banner>
    <detail-header></detail-header>
    <detail-list :list="list"></detail-list>
    <div class="center">

    </div>
  </div>
</template>

<script>
import detailBanner from './components/Banner'
import detailHeader from './components/Header'
import detailList from './components/List'
import axios from 'axios'
export default {
  name: 'Details',
  components: {
    detailBanner,
    detailHeader,
    detailList
  },
  data () {
    return {
      sightName: '',
      bannerImg: '',
      gallaryImgs: [],
      list: []
    }
  },
  methods: {
    getDetailsInfo () {
      axios.get('./static/mock/detail.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(this.getDetailsSucc)
    },
    getDetailsSucc (res) {
      res = res.data.data
      this.sightName = res.sightName
      this.bannerImg = res.bannerImg
      this.gallaryImgs = res.gallaryImgs
      this.list = res.categoryList
    }
  },
  mounted () {
    this.getDetailsInfo()
  }
}
</script>

<style lang="stylus" scoped>
  // @import '~styles/varibles.styl'
  // @import '~styles/mixins.styl'
  .center
    height 20rem
</style>
