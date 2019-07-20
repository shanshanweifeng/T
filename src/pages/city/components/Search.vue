<template>
  <div>
    <div class="search">
      <input class="search-input" v-model="keyword" type="text" placeholder="输入城市名或拼音" />
    </div>
    <div class="search-content" ref="search" v-show="keyword">
      <ul>
        <li class="search-item border-bottom" 
            v-for="item of list" 
            :key="item.id" @click="handCityClick(item.name)">
            {{item.name}}
        </li>
        <li class="search-item border-bottom" v-show="hasNOData">没有找到数据</li>
      </ul>
    </div>
  </div>
</template>

<script>
import Bscroll from "better-scroll";
export default {
  name: "CitySearch",
  props:{
      cityname: Object
  },
  data () {
      return {
          keyword:'',
          list:[],
          timer:null
      }
  },
  watch:{
      keyword () {
          if (this.timer) {
              clearTimeout(this.timer)
          }
          if (!this.keyword) {
              this.list = []
              return
          }
              this.timer = setTimeout(() =>{
                  const result = []
                  for (let i in this.cityname) {
                      this.cityname[i].forEach((value) => {
                          if (value.spell.indexOf(this.keyword) > -1 ||
                          value.name.indexOf(this.keyword) > -1) {
                              result.push(value)
                          }
                      }) 
                  }
                  this.list = result
              },100)
      }
  },
   methods:{
    handCityClick(city) {
      this.$store.dispatch('changeCity',city)
      this.$router.push('./')
    }
  },
  mounted () {
      this.scroll = new Bscroll(this.$refs.search)
  },
  computed :{
      hasNOData () {
          return !this.list.length
      }
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.search 
  height: 0.72rem;
  padding: 0 0.1rem;
  background: $bgColor;
  // background pink
  .search-input 
    width: 100%;
    height: 0.62rem;
    color: #616161;
    text-align: center;
    border-radius: 0.06rem;
    padding: 0 0.1rem;
    box-sizing: border-box;
.search-content
    overflow hidden  
    z-index 1
    position absolute
    top 1.58rem
    left 0
    right 0
    bottom 0
    background-color #eee
    .search-item
        line-height .62rem
        padding-left .2rem
        background-color #fff
        color #666
</style>
