<template>
  <div class="hot">
    <p class="hot-title">
      <span class="hot-title-left"><img src="http://img1.qunarzz.com/piao/fusion/1711/16/bfbb9874e8f11402.png"> 本周热门榜单</span>
      <span class="hot-title-right">全部榜单<span class="iconfont">&#xe62d;</span></span>
    </p>
    <div class="hot-body">
      <ul>
        <li v-for="item of list" :key="item.id">
          <div>
            <div class="hot-top" v-if="item.top">
              <img :src="item.top">
            </div>
            <img :src="item.imgUrl">
          </div>
          <p v-text="item.title"></p>
          <p><i>￥</i><u v-text="item.money"></u>起</p>
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
export default {
  name: 'homeHot',
  data: function () {
    return {
      list: [
        {
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1709/41/411f234d79457081a3.img.jpg_150x150_14d54b9c.jpg',
          top: 'http://img1.qunarzz.com/piao/fusion/1710/ab/159673b63e6ca702.png',
          title: '长隆野生动物世界',
          money: '173.01',
          id: '0001'
        }, {
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1603/3b/3bd311262ee06d8c90.img.jpg_150x150_97134a7a.jpg',
          top: 'http://img1.qunarzz.com/piao/fusion/1710/2d/36d0c4adaebbbc02.png',
          title: '广州长隆旅游度假区',
          money: '67.8',
          id: '0002'
        }, {
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1507/9e/7b5e0a44cb0310280b1aeb2a8dd94de8.water.jpg_150x150_03f4b403.jpg',
          top: 'http://img1.qunarzz.com/piao/fusion/1710/67/edc47ffef9e96b02.png',
          title: '长隆国际大马戏剧院',
          money: '268.01',
          id: '0003'
        }, {
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1707/ab/abb70c851caaa6d8a3.img.jpg_150x150_428d0c72.jpg',
          title: '长隆水上乐园',
          money: '96.7',
          id: '0004'
        }, {
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1707/47/477416df92210439a3.img.jpg_150x150_f41cda18.jpg',
          title: '长隆欢乐世界',
          money: '163.8',
          id: '0005'
        }, {
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1603/1c/1c67791edbe2677b90.img.jpg_150x150_4eb52b11.jpg',
          title: '珠江夜游',
          money: '178',
          id: '0006'
        }, {
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1603/ee/ee2fb567add7969390.water.jpg_150x150_afe1378c.jpg',
          title: '广州塔',
          money: '75',
          id: '0007'
        }, {
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1602/b2/b2af115356f50f6590.img.jpg_150x150_ad9a70e2.jpg',
          title: '岭南印象园',
          money: '52.01',
          id: '0008'
        }, {
          imgUrl: 'http://img1.qunarzz.com/sight/p0/201212/31/309a88f591369b6893835fbb.png_150x150_5be2f7a8.png',
          title: '广东科学中心',
          money: '29',
          id: '0009'
        }, {
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1709/5d/5d986aff376ff248a3.img.jpg_150x150_cb24c48b.jpg',
          title: '广州正佳极地海洋世界',
          money: '118',
          id: '0010'
        }
      ]
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
