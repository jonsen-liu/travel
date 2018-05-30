<template>
  <div class="details">
    <detail-banner></detail-banner>
  </div>
</template>

<script>
import detailBanner from './components/banner'
// import { mapState } from 'vuex'
export default {
  name: 'Details',
  components: {
    detailBanner
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
</style>
