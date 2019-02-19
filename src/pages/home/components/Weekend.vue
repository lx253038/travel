<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item of weekList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl">
        </div>
        <diV class="item-info">
          <p class="item-title">{{item.itemTitle}}</p>
          <p class="item-desc">{{item.itemDesc}}</p>
        </diV>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Weekend',
  props: {
    weekList: Array
  },
  data () {
    return {}
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.title
  line-height 0.8rem
  background #eee
  text-indent 0.2rem
  font-size 0.4rem
.item-img-wrapper
  overflow hidden
  height 0
  padding-bottom 36.9%
  .item-img
    width 100%
.item-info
  position relative
  padding 0.1rem 0.2rem 0.2rem 0.2rem
  .item-title
    line-height 0.5rem
    font-size 0.35rem
    ellipsis()
  .item-desc
    line-height 0.5rem
    color #ccc
    ellipsis()
</style>
