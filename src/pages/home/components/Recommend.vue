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
  data () {
    return {
      recomList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg',
        itemTitle: '故宫',
        itemDesc: '世界五大宫之首,穿越与您尽在咫尺',
        itemPrice: '20'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1901/97/97f793f8c9f37ac7a3.img.png_200x200_29601dba.png',
        itemTitle: '北京欢乐谷',
        itemDesc: '亚洲唯一飞行式过山车等你来挑战',
        itemPrice: '97.6'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1510/8e/8eea8eb6f41698290.img.jpg_200x200_595cfa1d.jpg',
        itemTitle: '金隅凤山温泉',
        itemDesc: '在温泉汤池中增添独享欢乐的私密空间',
        itemPrice: '248'
      }, {
        id: '0004',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1701/f6/f6159f9ebfb534aca3.img.jpg_200x200_5e71b24c.jpg',
        itemTitle: '鸟巢欢乐冰雪季',
        itemDesc: '刮起滑雪的传统与时尚的热潮',
        itemPrice: '106'
      }, {
        id: '0005',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1505/f5/f5f45e1a83537bcb.water.jpg_200x200_444cc7e8.jpg',
        itemTitle: '圆明园',
        itemDesc: '百年皇家的珍宝,民族耻辱的见证',
        itemPrice: '40'
      }, {
        id: '0006',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1505/8d/8d1f6d86b2c5926e.water.jpg_200x200_3235712b.jpg',
        itemTitle: '北京大观园',
        itemDesc: '红楼梦中走下来的建筑',
        itemPrice: '33.8'
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
