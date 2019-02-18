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
  data () {
    return {
      weekList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1811/f3/86173f863bef61.jpg_r_640x214_52b003ac.jpg',
        itemTitle: '京城周末撒欢',
        itemDesc: '在帝都过周末，不仅仅是城中游！'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1510/6e/1ea71e2f04e.jpg_r_640x214_aa6f091d.jpg',
        itemTitle: '京城有好泉',
        itemDesc: '细数北京温泉，温暖你的冬天'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1811/7e/476589267ebb41.jpg_r_640x214_bf599709.jpg',
        itemTitle: '京城溜娃必去',
        itemDesc: '德智体美劳全面发展的亲子日，这些地方该去看看…'
      }, {
        id: '0004',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/9e/21df651e19af5d.jpg_r_640x214_3ea5bb38.jpg',
        itemTitle: '寻找北京的皇城范儿',
        itemDesc: '数百年的宫廷庙宇，至今依旧威严霸气'
      }]
    }
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
