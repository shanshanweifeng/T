<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list :cities="cities" :hot="hotcities" :changeletter="getletter"></city-list>
    <city-alphabet :cities="cities" @letter-change="handletterchange" >
    </city-alphabet>
  </div>
</template>

<script>
import axios from "axios";
import CityHeader from "./components/Header";
import CitySearch from "./components/Search";
import CityList from "./components/List";
import CityAlphabet from "./components/Alphabet";
export default {
  name: "City",
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  data() {
    return {
      cities: {},
      hotcities: [],
      getletter:''
    };
  },
  methods: {
    getCityInfo() {
      axios.get("/api/city.json").then(this.handGetCityInfoSucc);
    },
    handGetCityInfoSucc(res) {
      res = res.data;
      if (res.ret && res.data) {
        this.cities = res.data.cities;
        this.hotcities = res.data.hotCities;
      }
    },
    handletterchange(letter) {
      this.getletter = letter
      // console.log(letter);
    }
  },
  mounted() {
    this.getCityInfo();
  }
};
</script>


<style lang="stylus" scoped></style>
