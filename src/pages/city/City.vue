<template>
  <div class="city">
    <city-header></city-header>
    <city-search :cities="cities"></city-search>
    <city-list :cities="cities" :hotcities="hotcities" :letter="letter"></city-list>
    <city-alphabet :cities="cities" @chenge="cityAlphabetChenge"></city-alphabet>
  </div>
</template>
<script>
import axios from 'axios'
import CityHeader from './components/CityHeader'
import CitySearch from './components/CitySearch'
import CityList from './components/CityList'
import CityAlphabet from './components/Alphabet'
export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  data () {
    return {
      cities: {},
      hotcities: [],
      letter: ''
    }
  },
  methods: {
    getCityinfo () {
      axios.get('/api/city.json')
        .then(this.handleGetCityInfo)
    },
    handleGetCityInfo (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.cities = data.cities
        this.hotcities = data.hotCities
      }
    },
    cityAlphabetChenge (letter) {
      this.letter = letter
    }
  },
  mounted () {
    this.getCityinfo()
  }
}
</script>

<style lang="stylus" scoped>

</style>
