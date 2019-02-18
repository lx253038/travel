<template>
  <div class="header">
    <div class="header-left">
       &nbsp;&nbsp;
      <span class="iconfont">&#xe624;</span>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>输入城市/景点/游玩主题
    </div>
    <div class="header-right">
      城市
      <span class="iconfont arrow-icon">&#xe64a;</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header
  display flex
  line-height 0.86rem
  background $bgColor
  color #ffffff
  .header-left
    width 0.64rem
    float left
  .header-right
    width 1.24rem
    float right
    text-align center
    .arrow-icon
      font-size 0.24rem
  .header-input
    flex 1
    height 0.64rem
    line-height 0.64rem
    margin-top 0.1rem
    margin-left 0.2rem
    background #ffffff
    border-radius 0.1rem
    color #cccccc
    padding-left 0.2rem
</style>
