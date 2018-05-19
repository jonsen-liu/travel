<template>
  <div class="weekend">
    <div class="weekend-title">周末去哪儿</div>
    <div class="weekend-middle" v-for="item of list" :key="item.id">
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
  data () {
    return {
      list: [
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/92/580e9ea4f37a1b.jpg_r_640x214_72112761.jpg',
          title: '广州必游TOP10',
          text: '感受现代与传统相融合的广州'
        }, {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1606/88/56f7f4bd0493fe.jpg_r_640x214_f8c0994a.jpg',
          title: '签到广州长隆',
          text: '来广州来长隆，就对了，就够了~'
        }, {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/50/07fa9343791682.jpg_r_640x214_c8c3d798.jpg',
          title: '自然户外好去处',
          text: '快快来到户外，感受花城的魅力'
        }, {
          id: '0004',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/ec/902725c4d56517.jpg_r_640x214_7a74d251.jpg',
          title: '羊城民俗风情游',
          text: '品味羊城文化，感受羊城别样风情'
        }, {
          id: '0005',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/6f/bf9ef732f8ad2e.jpg_r_640x214_c759559e.jpg',
          title: '宝贝亲子游乐地',
          text: '宝贝闲不住，我们去哪儿呀'
        }
      ]
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
