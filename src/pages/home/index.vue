<template>
  <div>
    <home-header></home-header>
    <home-swiper :swiperList="swiperList"></home-swiper>
    <home-icons :iconList="iconList"></home-icons>
    <home-recommend :recommendList="recommendList"></home-recommend>
    <home-weekend :weekendList="weekendList"></home-weekend>
  </div>
</template>
<script>
import HomeHeader from "./components/HomeHeader";
import HomeSwiper from "./components/Swiper";
import HomeIcons from "./components/icons";
import HomeRecommend from "./components/recommend";
import HomeWeekend from "./components/weekend";
import axios from "axios";
export default {
  name: "Home",
  data() {
    return {
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    };
  },
  components: { HomeHeader, HomeSwiper, HomeIcons, HomeRecommend, HomeWeekend },
  mounted() {
    this.getHomeInfor();
  },
  methods: {
    getHomeInfor() {
      axios.get("/static/index.json").then(this.getinfor);
    },
    getinfor(res) {
      const data = res.data.data;
      if (res.data.ret) {
        this.swiperList = data.swiperList;
        this.iconList = data.iconList;
        this.recommendList = data.recommendList;
        this.weekendList = data.weekendList;
      }
    }
  }
};
</script>
<style scoped>
</style>