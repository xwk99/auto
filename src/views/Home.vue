<template>
  <div>
    <home-header :city="city"></home-header>
    <home-weather :weather="weather" :weatherimg="weatherimg"></home-weather>
  </div>
</template>

<script>
import homeHeader from '@/components/Home/header.vue'
import homeWeather from '@/components/Home/weather.vue'
import axios from 'axios'

export default {
  name: 'Home',
  data () {
    return {
      city: '重庆',
      weather: {},
      weatherimg: []
    }
  },
  components: {
    homeHeader,
    homeWeather
  },
  methods: {
    getHomeInfo () {
      axios.get('https://v0.yiketianqi.com/api?version=v61&appid=17118356&appsecret=hUG7krLh&city=' + this.city + '&vue=1').then(this.getHomeInfoSucc)
      axios.get('/index-weather.json').then(this.getHomeWeatherInfoSucc)
    },
    getHomeInfoSucc (res) {
      this.weather = res.data
      console.log(this.weather.aqi)
    },
    getHomeWeatherInfoSucc (res) {
      this.weatherimg = res.data.data.weather
    }
  },
  activated () {
    this.getHomeInfo()
  }
}
</script>

<style lang="stylus" scoped>

</style>
