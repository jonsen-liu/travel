<template>
  <ul class="list">
    <li class="item"
    v-for="item of letters"
    :key="item"
    :ref="item"
    v-text="item"
    @click="listClick"
    @touchstart="listTouchstart"
    @touchmove="listTouchMove"
    @touchend="listTouchEnd"></li>
  </ul>
</template>
<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  },
  computed: {
    letters () {
      const letters = []
      for (let key in this.cities) {
        letters.push(key)
      }
      return letters
    }
  },
  data () {
    return {
      touchStatus: false,
      startY: '',
      time: null
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  methods: {
    listClick (e) {
      this.$emit('chenge', e.target.innerText)
    },
    listTouchstart () {
      this.touchStatus = true
    },
    listTouchMove (e) {
      if (this.touchStatus) {
        if (this.time) {
          clearTimeout(this.time)
        }
        this.time = setTimeout(() => {
          const touchY = e.touches[0].clientY - 78
          const index = Math.floor((touchY - this.startY) / 20)
          this.$emit('chenge', this.letters[index])
          clearTimeout(this.time)
        }, 16)
      }
    },
    listTouchEnd () {
      this.touchStatus = false
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.list {
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: absolute;
  top: 1.58rem;
  right: 0;
  bottom: 0;
  width: 0.4rem;

  .item {
    text-align: center;
    line-height: 0.4rem;
    color: $bgColor;
  }
}
</style>
