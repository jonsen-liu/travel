<template>
  <div class="weekend">
    <div class="weekend-title">周末去哪儿</div>
    <div class="weekend-middle" v-for="item of weekendList" :key="item.id">
      <div>
        <img :src="item.imgUrl">
      </div>
      <div class="weekend-middle-title" v-text="item.title"></div>
      <div class="weekend-middle-text" v-text="item.text"></div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'weekend',
  props: {
    weekendList: Array
  },
  data () {
    return {
      list: []
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.yellow {
  color $seyTextColor;
}

.weekend-title {
  height .86rem
  line-height .86rem
  font-size .32rem
  padding-left .28rem
}
.weekend-middle{
  background-color $bgColorWhite
  height 4.4rem
  margin-bottom .2rem
  img{
    width 100%
  }
  .weekend-middle-title{
    padding-left .28rem
    margin-top .28rem
    font-size .32rem
  }
  .weekend-middle-text{
    padding-left .28rem
    margin-top .16rem
    font-size .16rem
  }
}
</style>
