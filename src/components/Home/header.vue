<template>
    <div>
        <div class="header">
          <div class="header-home">首页</div>
          <div class="header-location">
              <span class="iconfont">&#xe611;</span>
              <div>重庆</div>
          </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'homeHeader'
}
</script>

<style lang="stylus" scoped>
@import '../../assets/styles/background.styl'
  .header >>> .iconfont
    padding-right: .1rem
  .header
    width: 100%
    height: 1rem
    display: flex
    background: $bgcolor
    .header-home
      line-height: 1rem
      text-align: center
      width: 100%
      font-size: .4rem
    .header-location
      position: absolute
      right: 0rem
      top: 0
      width: 2rem
      display: inherit
      line-height: 1rem
      font-size: .32rem
      justify-content: center
</style>
