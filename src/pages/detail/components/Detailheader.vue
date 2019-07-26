<template>
  <div class="detail">
    <router-link tag="div" to="/" class="detail-back" v-show="!showtitle">
      <div class="iconfont Detailback-icon">&#xe624;</div>
    </router-link>
    <div class="detail-title" v-show="showtitle" :style="opacitystyle">
      <router-link tag="div" to="/">
        <div class="iconfont detail-fix-back">&#xe624;</div>
      </router-link>景点详情
    </div>
  </div>
</template>

<script>
export default {
  name: "Detailheader",
  data () {
    return {
      showtitle: false,
      opacitystyle:{
        opacity:0
      } 
    }
  },
  methods:{
    handlescroll() {
      const top = document.documentElement.scrollTop
      if (top>60) {
        const opacity = top/140
        this.opacitystyle = {
          opacity : opacity
        }
        this.showtitle = true
      }else{
        this.showtitle = false
      }
    }
  },
  activated () {
    window.addEventListener('scroll',this.handlescroll)
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.detail-back {
  position: absolute;
  left: 0.2rem;
  top: 0.2rem;
  width: 0.8rem;
  height: 0.8rem;
  line-height: 0.8rem;
  text-align: center;
  border-radius: 0.4rem;
  background: rgba(0, 0, 0, 0.5);

  .Detailback-icon {
    color: #fff;
    font-size: 0.4rem;
  }
}

.detail-title {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  // width 100%
  // overflow: hidden;
  height: 0.86rem;
  line-height: 0.86rem;
  text-align: center;
  color: #fff;
  background: $bgColor;
  font-size: 0.3rem;

  .detail-fix-back {
    position: absolute;
    left: 0;
    top: 0;
    width: 0.8rem;
    text-align: center;
    font-size: 0.33rem;
    color #fff
  }
}
</style>
