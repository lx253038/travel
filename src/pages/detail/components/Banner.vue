<template>
  <div>
    <div class="banner" @click="handleClickImg">
      <img
        class="banner-img"
        src="//img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_600x330_f922b488.jpg"
      >
      <div class="banner-info">
        <div class="banner-title">故宫(AAAAA景区)</div>
        <div class="banner-num">
          <span class="iconfont banner-icon">&#xe67b;</span> 8
        </div>
      </div>
    </div>
    <common-gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  data () {
    return {
      showGallary: false,
      imgs: ['http://img1.qunarzz.com/sight/p55/201211/04/fbcab3e5d6479ce893835fbb.jpg_r_800x800_6360f514.jpg',
        'http://img1.qunarzz.com/sight/p0/1501/af/af47583adca3f972.water.jpg_r_800x800_5a57e1fe.jpg',
        'http://img1.qunarzz.com/sight/p0/1410/e3/73da8d3e19cdc41c1932d4fcd22ec792.water.jpg_r_800x800_7f96ccf9.jpg']
    }
  },
  components: {
    CommonGallary
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
