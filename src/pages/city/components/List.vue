<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">{{this.$store.state.city}}</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper" 
               v-for="item of hot" 
               :key="item.id" 
               @click="handCityClick(item.name)">
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area" v-for="(item,key) of cities" :key="key" :ref="key">
        <div class="title border-topbottom">{{key}}</div>
        <div class="item-list">
          <div
            class="item border-bottom"
            v-for="inneritem of item"
            :key="inneritem.id"
            @click="handCityClick(inneritem.name)"
          >{{inneritem.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from "better-scroll";
export default {
  name: "CityList",
  props: {
    cities: Object,
    hot: Array,
    changeletter: String
  },
  methods:{
    handCityClick(city) {
      this.$store.dispatch('changeCity',city)
      this.$router.push('./')
    }
  },
  mounted() {
    this.scroll = new Bscroll(this.$refs.wrapper);
  },
  watch: {
    changeletter() {
      // console.log(this.changeletter);
      // alert("adasd");
      if (this.changeletter) {
        const element = this.$refs[this.changeletter][0]
        this.scroll.scrollToElement(element) 
      }
    }
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.border-topbottom {
  &:before {
    border-color: #CCC;
  }

  &:after {
    background-color: #CCC;
  }
}

.border-topbottom {
  &:before {
    border-color: #CCC;
  }
}

.list {
  overflow: hidden;
  position: absolute;
  top: 1.58rem;
  left: 0;
  right: 0;
  bottom: 0;

  .title {
    line-height: 0.54rem;
    background: #eee;
    padding-left: 0.2rem;
    color: #666;
  }

  .button-list {
    overflow: hidden;
    padding: 0.1rem 0.4rem 0.1rem 0.1rem;

    // margin: 0 auto;
    .button-wrapper {
      float: left;
      width: 33.33%;

      .button {
        margin: 0.1rem;
        padding: 0.1rem 0;
        text-align: center;
        border-radius: 0.06rem;
        border: 0.02rem solid #ccc;
      }
    }
  }

  .item-list {
    .item {
      line-height: 0.76rem;
      padding-left: 0.2rem;
    }
  }
}
</style>
