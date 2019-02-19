<template>
  <div>
    <div class="header">
      <router-link to="/">
        <span class="iconfont header-back">&#xe624;</span>
      </router-link>城市选择
    </div>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header
  position relative
  height $headerHeight
  overflow hidden
  line-height $headerHeight
  text-align center
  color #ffffff
  background $bgColor
  font-size 0.32rem
  .header-back
    position absolute
    top 0
    left 0
    width 0.64rem
    text-align center
    font-size 0.36rem
    color #fff
</style>
