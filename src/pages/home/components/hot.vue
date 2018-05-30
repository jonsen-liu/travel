<template>
  <div class="hot">
    <p class="hot-title">
      <span class="hot-title-left"><img src="http://img1.qunarzz.com/piao/fusion/1711/16/bfbb9874e8f11402.png"> 本周热门榜单</span>
      <span class="hot-title-right">全部榜单<span class="iconfont">&#xe62d;</span></span>
    </p>
    <div class="hot-body">
      <ul>
        <router-link
        tag="li"
        v-for="item of Hot"
        :key="item.id"
        :to="'/details/' + item.id">
          <div>
            <div class="hot-top" v-if="item.top">
              <img :src="item.top">
            </div>
            <img :src="item.imgUrl">
          </div>
          <p v-text="item.title"></p>
          <p><i>￥</i><u v-text="item.money"></u>起</p>
        </router-link>
      </ul>
    </div>
  </div>
</template>
<script>
export default {
  name: 'homeHot',
  props: {
    Hot: Array
  },
  data: function () {
    return {

    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
@import '~styles/mixins.styl'
  .hot{
    height 4.02rem
    margin-top 10px
    background-color $bgColorWhite
    .hot-title{
      overflow hidden
      height .9rem
      line-height .9rem
      .hot-title-left{
        float left
        padding-left .2rem
        font-size 0.32rem
        font-weight 600
        img{
          position relative
          top -.1rem
          width .35rem
        }
      }
      .hot-title-right{
        float right
        font-size 0.25rem
        padding-right .3rem
        span {
          font-size 0.25rem
        }
      }
    }
    .hot-body{
      height 3.12rem
      overflow-x scroll
      padding 0 .3rem
      ul{
        width 21rem
        padding .1rem .2rem 0 0
        li{
          float left
          width 2rem
          height 100%
          margin-right .1rem
          font-size .25rem
          div{
            position relative
            margin-bottom .1rem
            .hot-top{
              position absolute
              top -.1rem
              width .8rem
              img{
                width 100%
              }
            }
            img{
              width 100%
            }
          }
          p{
            padding .1rem 0 0
            text-align center
            font-size .2rem
            ellipsis()
            i{
              color $seyTextColor
            }
            u{
              font-size .3rem
              color $seyTextColor
            }
          }
        }
      }
    }

  }

</style>
