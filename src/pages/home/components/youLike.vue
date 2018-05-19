<template>
  <div class="like">
    <div class="like-title">
      <img src="http://img1.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png">
      <span>
        猜你喜欢
      </span>
    </div>
    <div class="like-body">
      <ul>
        <li v-for="item of youLike" :key="item.id">
          <div class="list-left">
            <div class="list-img-title list-img-title-urlhuang" v-if="item.titleText==0">
              即买即用
            </div>
            <div class="list-img-title list-img-title-urllan" v-else>
              可定明日
            </div>
            <img :src="item.imgUrl">
          </div>
          <div class="list-right">
            <p class="list-right-title" v-text="item.title"></p>
            <div class="list-right-middle">
              <span class="list-right-xinxin">
                <span class="iconfont yellow" v-for="num of item.xinxin" :key="num.id">&#xe633;</span>
                <span class="iconfont" v-for="num of 5-item.xinxin" :key="num.id">&#xe633;</span>
              </span>
              <span class="list-right-pinglun" v-if="item.pinglun != 0">{{item.pinglun}}条评论</span>
            </div>
            <div class="list-right-bottom">
              <span class="money-text"><i>￥</i><em v-text="item.money"></em></span>起
              <span class="bottom-text" v-text="item.site"></span>
            </div>
          </div>
        </li>
      </ul>
    </div>
    <div class="like-foot">
      <a href="http://www.haidu.com">查看所有产品</a>
    </div>
  </div>
</template>
<script>
export default {
  name: 'youLike',
  props: {
    youLike: Array
  },
  data: function () {
    return {
      list: []
    }
  },
  computed: {
  //   xinxins () {
  //     var lists = this.list;
  //     const xinxin = []
  //     for (var i = 0; i < lists.length; i++){
  //       for(var k = 0; k < lists[i].xinxin; k++){

  //       }
  //     }
  //   }
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl'
@import '~styles/mixins.styl'
.list-img-title-urlhuang{
  background url(https://img1.qunarzz.com/piao/fusion/1802/20/2ba6d10b17972e02.png) no-repeat
}
.list-img-title-urllan{
  background url(https://img1.qunarzz.com/piao/fusion/1802/52/b9080e45b69b4f02.png) no-repeat
}
.yellow{
  color $seyTextColor
}
.like{
  background-color $bgColorWhite
  .like-title{
    height .8rem
    line-height .8rem
    // background-color #ccc
    padding-left .2rem
    margin-top 10px
    img{
      position relative
      top -.1rem
      width .3rem
    }
    span{
      font-size .32rem
    }
  }
  .like-body{
    ul{
      padding-left .3rem
      li{
        overflow hidden
        height 2.4rem
        padding .2rem 0
        border-bottom 1px solid $homebgcolor
        box-sizing border-box
        .list-left{
          float left
          position relative
          margin-right .2rem
          .list-img-title{
            position absolute
            top 0
            width 1rem
            height .4rem
            line-height .4rem
            font-size .16rem
            color #fff
            background-size 100%
          }
          img{
            width 2rem
          }
        }
        .list-right{
          overflow hidden
          .list-right-title{
            font-size .32rem
            padding-top .3rem
          }
          .list-right-middle{
            padding-top .2rem
            font-size .2rem;
            .list-right-xinxin{
              color #e0e0e0
              font-size .2rem
              margin-right .1rem
            }
            .list-right-pinglun{
              color #616161
            }
          }
          .list-right-bottom{
            padding-top .3rem
            color #616161
            font-size .24rem
            .money-text{
              color $seyTextColor
              i{
                font-size .24rem
              }
              em{
                font-size .48rem
              }
            }
            .bottom-text{
              float right
              line-height .64rem
              margin-right .3rem
              ellipsis()
            }
          }
        }
      }
    }
  }
}
.like-foot{
  text-align center
  a{
    display block
    padding .25rem
  }
}
</style>
