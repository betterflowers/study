<template>
  <div>
    <home-header></home-header>
    <home-swiper :swiperList="swiperList"></home-swiper>
    <home-icons :List="iconList"></home-icons>
    <home-recommend :recommendList="recommendList"></home-recommend>
    <home-weekend :weekendList="weekendList"></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'
import axios from 'axios'
export default {
  name: 'Home',
  //引入局部组件，注册到Home的组件中，ES6中key和value都一样，可省略为一
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  data () {
    return {
      lastCity: '',
      swiperList: [],
      iconList: [],
      weekendList: [],
      recommendList: []
    }
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json?city=' + this.$store.state.city)
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      //获取数据的内容
      res = res.data
      //如果后端正确的返回了结果，并且res有data
      if (res.ret && res.data) {
        const data = res.data
        this.weekendList = data.weekendList
        this.swiperList = data.swiperList
        this.recommendList = data.recommendList
        this.iconList = data.iconList
      }
      console.log(res)
    }
  },
  mounted () {
    this.lastCity = this.$store.state.city
    this.getHomeInfo()
  },
  activated () {
    if (this.lastCity !== this.$store.state.city) {
      this.lastCity = this.$store.state.city
      this.getHomeInfo()
    }
  }
}
</script>
<style scoped>
</style>
