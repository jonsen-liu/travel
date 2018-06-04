<template>
  <div class="details-list">
    <div v-for="(item, index) of list" :key="index">
      <div class="item">
        <span class="item-title-icon"></span>
        {{item.title}}
      </div>
      <div v-if="item.children" class="item-children">
        <details-list :list="item.children"></details-list>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'detailsList',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  .item
    line-height .8rem
    font-size .32rem
    padding 0 .24rem
    border-bottom 1px solid #ddd
  .item-title-icon
    position relative
    top .08rem
    left .08rem
    display: inline-block;
    width: .36rem;
    height: .36rem;
    background: url(//s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat;
    margin-right: .1rem;
    background-size: .4rem 3rem;
  .item-children
    padding-left .24rem
</style>
