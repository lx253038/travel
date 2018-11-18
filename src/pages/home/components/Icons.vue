<template>
  <div class="icons">
    <div class="icon" v-for="item of iconList" :key="item.iconId1">
      <div class="imgDiv">
        <img class="icon-img" :src="item.iconUrl">
      </div>
      <p class="iconName">{{item.iconName}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      iconList: [{
        iconId: '0001',
        iconName: '景点门票',
        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png'
      }, {
        iconId: '0002',
        iconName: '一日游',
        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png'
      }, {
        iconId: '0003',
        iconName: '北京必玩',
        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png'
      }, {
        iconId: '0004',
        iconName: '溜娃儿',
        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/47/c2b659e048b11602.png'
      }, {
        iconId: '0005',
        iconName: '爬长城',
        iconUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20191/0334cf5430b9b5505fd79e2b8d7e8670.png'
      }, {
        iconId: '0006',
        iconName: '故宫',
        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/6c/9e54a8540fee0102.png'
      }, {
        iconId: '0007',
        iconName: '北京庙会',
        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/b2/bfbc5d66e0ab5a02.png'
      }, {
        iconId: '0008',
        iconName: '冰雪季',
        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/fc/b10a6b2e4f0fe102.png'
      }, {
        iconId: '0009',
        iconName: '泡温泉',
        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png'
      }]
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
.icons
  overflow hidden
  height 0
  padding-bottom 50%
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
</style>
