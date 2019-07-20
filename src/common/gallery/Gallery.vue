<template>
  <div class="container" @click="handGalleryclick">
    <div class="wrapper">
      <swiper :options="swiperOption">
        <swiper-slide v-for="(item,id) in chuandiimgs" :key="id">
          <img class="swiper-img" :src="item.imgUrl"/>
        </swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: "CommonGallery",
  props:{
      chuandiimgs:Array
  },
  data () {
      return {
          swiperOption: {
          pagination: '.swiper-pagination',
          paginationType: 'fraction',
          observeParents: true,
          observer: true,
          loop: true,
          autoplay:2000
      }
      }
  },
  methods:{
      handGalleryclick() {
          this.$emit('close')
      }
  }
};
</script>

<style lang="stylus" scoped>
.container >>> .swiper-container{
    overflow inherit
    }
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  z-index: 99;
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  background: #000;

  .wrapper {
    width 100%
    height 0
    padding-bottom 66.37%
    // background-color #fff
  }
    .swiper-img{
        width 100%
    }
    .swiper-pagination{
        color #fff
        bottom -1rem
    }  
}
</style>
