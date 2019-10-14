<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list :cities="cities" :hotCities="hotCities"></city-list>
    <city-alphabet :cities="cities"></city-alphabet>
  </div>
</template>
<script>
import CityHeader from "./components/cityHeader";
import CitySearch from "./components/search";
import CityList from "./components/list";
import CityAlphabet from "./components/alphabet";
import axios from "axios";

export default {
  name: "City",
  components: { CityHeader, CitySearch, CityList, CityAlphabet },
  data() {
    return {
      cities: {},
      hotCities: []
    };
  },
  mounted() {
    this.getCityInfor();
  },
  methods: {
    getCityInfor() {
      axios.get("/static/city.json").then(this.getInfor);
    },
    getInfor(res) {
      res = res.data;
      if (res.ret && res.data) {
        this.cities = res.data.cities;
        this.hotCities = res.data.hotCities;
      }
    }
  }
};
</script>
<style lang="stylus" scoped></style>