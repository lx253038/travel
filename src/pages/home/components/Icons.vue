<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="(page, index) of pages" :key="index+1">
        <div class="icon" v-for="item of page" :key="item.iconId">
          <div class="imgDiv">
            <img class="icon-img" :src="item.iconUrl">
          </div>
          <p class="iconName">{{item.iconName}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    iconList: Array
  },
  data () {
    return {
      swiperOption: {}
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
@import '~styles/mixins.styl'
.icons
  overflow hidden
  height 0
  padding-bottom 50%
  margin-top 0.1rem
  .icon
    position relative
    float left
    width 25%
    padding-bottom 25%
    .imgDiv
      position absolute
      top 0
      left 0
      right 0
      bottom 0.44rem
      padding 0.1rem
      .icon-img
        height 100%
        display block
        margin 0 auto
    .iconName
      position absolute
      left 0
      right 0
      bottom 0
      height 0.44rem
      line-height 0.44rem
      color $darkTextColor
      text-align center
      ellipsis()
</style>
