<template>
  <div>
    <HomeHeader></HomeHeader>
    <HomeSwiper :list="swiperList"></HomeSwiper>
    <HomeIcons :list="iconList"></HomeIcons>
    <HomeRecommend :list="RecommendList"></HomeRecommend>
    <HomeWeekend :list="WeekendList"></HomeWeekend>
  </div>
</template>

<script>
import HomeHeader from "./components/Header";
import HomeSwiper from "./components/Swiper";
import HomeIcons from "./components/Icons";
import HomeRecommend from "./components/Recommend";
import HomeWeekend from "./components/Weekend";
// import axios from "axios"
export default {
  name: "Home",
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  data (){
    return {
      swiperList:[],
      iconList:[],
      RecommendList:[],
      WeekendList:[]
    }
  },
  methods: {
    getHomeInfo () {
      this.$http.get('/api/index.json')
      .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (a) {
      var res;
      res=a.data
      if (res.ret && res.data) {
        this.swiperList = res.data.swiperList;
        this.iconList = res.data.iconList;
        this.RecommendList = res.data.recommendList
        this.WeekendList = res.data.weekendList
      }
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>

<style>
</style>

