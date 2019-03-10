<template>
  <div>
    <router-link tag="div" to="/" class="header-abs" v-show="showabs">
      <span class="iconfont header-abs-back">&#xe61e;</span>
    </router-link>
    <div class="header-fixed" v-show="!showabs" :style="opacityStyle">
      <router-link to="/">
        <span class="iconfont header-back">&#xe61e;</span>
      </router-link>景点详情
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showabs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 20) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.showabs = false
      } else {
        this.showabs = true
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header-abs
  position absolute
  left 0.1rem
  top 0.1rem
  width 0.7rem
  height 0.7rem
  line-height 0.7rem
  text-align center
  border-radius 0.4rem
  background rgba(0, 0, 0, 0.6)
  .header-abs-back
    color #ffffff
    font-size 0.5rem
.header-fixed
  position fixed
  top 0
  left 0
  right 0
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
