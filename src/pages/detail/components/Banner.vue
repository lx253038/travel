<template>
  <div>
    <div class="banner" @click="handleClickImg">
      <img class="banner-img" :src="bannerImg">
      <div class="banner-info">
        <div class="banner-title">{{sightName}}</div>
        <div class="banner-num">
          <span class="iconfont banner-icon">&#xe67b;</span> 8
        </div>
      </div>
    </div>
    <fade-animation>
      <common-gallary :imgs="gallaryImgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
    </fade-animation>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
import FadeAnimation from 'common/fade/FadeAnimation'
export default {
  name: 'DetailBanner',
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
  },
  data () {
    return {
      showGallary: false
    }
  },
  components: {
    CommonGallary,
    FadeAnimation
  },
  methods: {
    handleClickImg () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  }

}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.banner
  position relative
  overflow hidden
  height 0
  padding-bottom 55%
  .banner-img
    width 100%
  .banner-info
    position absolute
    left 0
    right 0
    bottom 0
    line-height 0.6rem
    display flex
    color #fff
    background-image linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
    .banner-title
      font-size 0.36rem
      padding 0 0.2rem
      flex 1
    .banner-num
      padding 0 0.35rem
      line-height 0.4rem
      height 0.4rem
      border-radius 0.3rem
      background rgba(0, 0, 0, 0.8)
      font-size 0.24rem
      margin-top 0.14rem
      margin-right 0.2rem
      .banner-icon
        font-size 0.24rem
</style>
