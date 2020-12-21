<template>
    <div>
        <div class="weather">
            <div class="weather-date">
                <div>{{weather.date}}</div>
                <div>{{weather.week}}</div>
                <div>设置<span class="iconfont">&#xe612;</span></div>
            </div>
            <div class="weather-img">
                <img :src="img" />
            </div>
            <div class="weather-title">
                <div class="weather-title-temperature">{{weather.tem}}</div>
                <div class="weather-title-icon">°C</div>
                <div class="weather-title-weather">{{weather.wea}}</div>
            </div>
            <ul>
                <li class="weather-line">{{weather.tem2}} ~ {{weather.tem1}} °C</li>
                <li class="weather-line">{{weather.win}} {{weather.win_speed}}</li>
                <li class="weather-line">空气： {{weather.air_level}}</li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
  name: 'homeWeather',
  props: {
    weather: Object,
    weatherimg: Array
  },
  computed: {
    img () {
      var img = ''
      this.weatherimg.forEach((item) => {
        if (this.weather.wea_img === item.spell) {
          img = item.img
        }
      })
      return img
    }
  }
}
</script>

<style lang="stylus" scoped>
    .weather
        width: 100%
        height: 5.8rem
        background: #a1b8ca
        .weather-date
            height: 1rem
            background-image: linear-gradient(to top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.3))
            color: #ffffff
            padding: .32rem 0 0 0
            display: flex
            justify-content: space-around
            font-size: .32rem
        .weather-img
            height: 1rem
            width: 100%
            text-align: center
        .weather-title
            color: #ffffff
            height: 1.5rem
            display: flex
            justify-content: center
            .weather-title-temperature
                font-size: 1rem
                line-height: 1.5rem
                width: 1.2rem
                text-align: center
            .weather-title-icon
                height: 1rem
                line-height: 1rem
                margin-right: .2rem
            .weather-title-weather
                height: 1.2rem
                line-height: 1.2rem
                font-size: .6rem
                align-self: flex-end
        .weather-line
            height: .66rem
            line-height: .66rem
            text-align: center
            color: #ffffff
</style>
