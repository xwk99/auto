<template>
  <div>
    <home-header :city="city"></home-header>
  </div>
</template>

<script>
import homeHeader from '@/components/Home/header.vue'
import axios from 'axios'

export default {
  name: 'Home',
  data () {
    return {
      city: '重庆'
    }
  },
  components: {
    homeHeader
  },
  methods: {
    getHomeInfo () {
      axios.get('https://v0.yiketianqi.com/api?version=v61&appid=17118356&appsecret=hUG7krLh&city=' + this.city + '&vue=1').then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      console.log(res.data)
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>

<style lang="stylus" scoped>

</style>
