<template>
  <div>
    <bannerimg></bannerimg>
    <Detailheader></Detailheader>
    <div class="content">
      <Detaillist :list="categoryList"></Detaillist> 
    </div> 
  </div>
</template>

<script>
import bannerimg from "./components/banner.vue";
import Detailheader from "./components/Detailheader.vue";
import Detaillist from "./components/List.vue";
import axios from "axios"

export default {
  name: "Detail",
  components: {
    bannerimg,
    Detailheader,
    Detaillist
  },
  data () {
    return {
    categoryList: []
    }
  },
  methods:{
    getDetailInfo () {
      axios.get('/api/detail.json',{
        params:{
          id: this.$route.params.id
        }
      })
      .then (this.handleGetDataSucc)
    },
    handleGetDataSucc(res) {
      res =  res.data
      if(res.ret && res.data){
        const data = res.data
        this.categoryList = data.categoryList
        console.log(this.categoryList)
      }
    }
  },
  mounted () {
    this.getDetailInfo()
  }
};
</script>

<style lang="stylus" scoped>
  .content
    height 50rem
</style>
