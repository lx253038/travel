<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of recomList" :key="item.id">
        <img class="item-img" :src="item.imgUrl">
        <diV class="item-info">
          <p class="item-title">{{item.itemTitle}}</p>
          <p class="item-desc">{{item.itemDesc}}</p>
          <p class="item-price">
            <span class="fuhao">¥</span>
            <span class="number">{{item.itemPrice}}</span>起
          </p>
        </diV>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    recomList: Array
  },
  data () {
    return {}
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.title
  margin-top 0.2rem
  line-height 0.8rem
  background #eee
  text-indent 0.2rem
  font-size 0.4rem
.item
  display flex
  height 2rem
  overflow hidden
  .item-img
    height 1.8rem
    width 1.8rem
    padding 0.1rem
  .item-info
    flex 1
    padding 0.2rem
    min-width 0
    .item-title
      line-height 0.6rem
      font-size 0.4rem
      ellipsis()
    .item-desc
      line-height 0.6rem
      color #ccc
      ellipsis()
    .item-price
      line-height 0.5rem
      color #ccc
      font-size 0.24rem
      .fuhao
        font-size 0.24rem
        color #ff8300
      .number
        font-size 0.4rem
        color #ff8300
</style>
