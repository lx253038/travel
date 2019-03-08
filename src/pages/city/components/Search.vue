<template>
  <div>
    <div class="search">
      <input v-model="keyword" class="search-input" type="text" placeholder="输入城市名或拼音">
    </div>
    <div class="search-content" v-show="keyword" ref="search">
      <ul>
        <li
          @click="handleCityClick(item.name)"
          class="search-item border-bottom"
          v-for="item of list"
          :key="item.id"
        >{{item.name}}</li>
        <li class="search-end border-bottom" v-show="hasNoData">没有搜索到匹配数据</li>
      </ul>
    </div>
  </div>
</template>

<script>
import Bscoll from 'better-scroll'
import { mapMutations } from 'vuex'
export default {
  name: 'CitySearch',
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  props: {
    cities: Object
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach(city => {
            if (city.spell.indexOf(this.keyword) > -1 || city.name.indexOf(this.keyword) > -1) {
              result.push(city)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  mounted () {
    this.scroll = new Bscoll(this.$refs.search)
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  },
  methods: {
    handleCityClick (city) {
      // this.$store.commit('changeCity', city)
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.search
  height 0.72rem
  background $bgColor
  padding 0 0.1rem
  .search-input
    box-sizing border-box
    padding 0 0.1rem
    height 0.62rem
    line-height 0.62rem
    width 100%
    text-align center
    border-radius 0.06rem
    color #666
.search-content
  z-index 1
  overflow hidden
  position absolute
  top 1.58rem
  left 0
  right 0
  bottom 0
  background #eee
  .search-item
    line-height 0.8rem
    padding-left 0.2rem
    color #666
    background #fff
  .search-end
    line-height 0.62rem
    text-align center
    color #666
    background #fff
</style>
