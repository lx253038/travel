<template>
  <div class="header">
    <div class="header-left">
      &nbsp;&nbsp;
      <span class="iconfont">&#xe61e;</span>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe622;</span>输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{this.city}}
        <span class="iconfont arrow-icon">&#xe64a;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city'])
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header
  display flex
  line-height $headerHeight
  background $bgColor
  color #ffffff
  .header-left
    width 0.6rem
    float left
  .header-right
    min-width 1.24rem
    margin-left 0.1rem
    margin-right 0.1rem
    float right
    text-align center
    color #fff
    font-size 0.3rem
    .arrow-icon
      font-size 0.28rem
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
