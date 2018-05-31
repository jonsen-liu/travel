<template>
  <div class="details">
    <detail-banner></detail-banner>
    <detail-header></detail-header>
    <div class="center">

    </div>
  </div>
</template>

<script>
import detailBanner from './components/Banner'
import detailHeader from './components/Header'
// import { mapState } from 'vuex'
export default {
  name: 'Details',
  components: {
    detailBanner,
    detailHeader
  }
}
</script>

<style lang="stylus" scoped>
  // @import '~styles/varibles.styl'
  // @import '~styles/mixins.styl'
  .center
    height 20rem
</style>
