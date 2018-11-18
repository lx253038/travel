<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgURL">
      </swiper-slide>

      <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination"></div>
      <!-- 向前箭头 -->
      <!-- <div class="swiper-button-prev" slot="button-prev"></div>  -->
      <!-- 向后箭头 -->
      <!-- <div class="swiper-button-next" slot="button-next"></div> -->
      <!-- 滚动条 -->
      <!-- <div class="swiper-scrollbar" slot="scrollbar"></div> -->
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '0001',
        imgURL: 'http://img1.qunarzz.com/piao/fusion/1811/31/da037478f37cf202.jpg_750x200_fe28d396.jpg'
      }, {
        id: '0002',
        imgURL: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20192/c64e6f7308f67f0862adb64b9d9fcff0.jpg_750x200_37c4c320.jpg'
      }, {
        id: '0003',
        imgURL: 'http://img1.qunarzz.com/piao/fusion/1808/70/5603e6a535062402.jpg_750x200_2c552f2c.jpg'
      }, {
        id: '0004',
        imgURL: 'http://img1.qunarzz.com/piao/fusion/1812/d6/daa880b254940402.jpg_750x200_b114308a.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active
  background #ffffff
.wrapper
  overflow hidden
  width 100%
  height 0
  padding-bottom 26.67%
  background #eeeeee
  .swiper-img
    width 100%
</style>
