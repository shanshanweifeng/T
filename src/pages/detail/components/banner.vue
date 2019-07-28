<template>
   <div>
        <div class="banner" @click="handbannerclick">
      <img class="banner-img" src="//img1.qunarzz.com/sight/p0/201405/14/3dfad2bcd30c40e91a15f8b7296d86a6.jpg_600x330_98874a40.jpg" alt="同里古镇">
      <div class="banner-info">
          <div class="banner-title">
              同里古镇(AAAAA景区)
          </div>
          <div class="banner-number">
              <span class="iconfont">&#xe692;</span>
              30
          </div>
      </div>
    </div>
    <Fade>
        <CommonGallery :chuandiimgs="imgs" v-show="showGallery" @close="handGalleryclose" class="imgscenter"></CommonGallery>
    </Fade>
    
   </div>
</template>

<script>
import CommonGallery from 'common/gallery/Gallery'
import Fade from 'common/fade/Fade'
import axios from "axios"
export default {
    name: 'bannerimg',
    data () {
        return {
            showGallery:false,
            imgs:['http://img1.qunarzz.com/sight/p0/201405/14/3dfad2bcd30c40e91a15f8b7296d86a6.jpg_r_800x800_891d0af7.jpg','http://img1.qunarzz.com/sight/p0/1805/83/839c53b2f1c3f6a0a3.water.jpg_r_800x800_9999f959.jpg','http://img1.qunarzz.com/sight/p0/1805/7d/7d56b6daec39df28a3.water.jpg_r_800x800_a98b36dc.jpg']
        }
    },
    methods:{
        handbannerclick () {
            this.showGallery = true
        },
        handGalleryclose () {
            this.showGallery = false
        },
        getBannerImgInfo () {
            axios.get('/api/index.json')
            .then(this.getHomeInfoSucc)
        },
        getHomeInfoSucc (b) {
            var rest 
            rest = b.data
            if (rest.ret && rest.data) {
                this.imgs = rest.data.imgs
            }
        }
    },
    components:{
        CommonGallery,
        Fade
    },
    mounted () {
    this.getBannerImgInfo()
  } 
}
</script>

<style lang="stylus" scoped>
    .banner
        position relative
        overflow hidden
        height 0
        padding-bottom 55%
        .banner-img
            width 100%
        .banner-info
            color  #fff 
            display flex
            position absolute    
            left 0
            right 0
            bottom 0
            line-height .8rem
            padding 0 .4rem
            .banner-title
                flex 1
                font-size .36rem
            .banner-number
                margin-top .25rem
                padding 0 .4rem
                line-height .32rem
                height .32rem    
                border-radius .2rem
                background rgba(0,0,0,.8)
                font-size .24rem
    .imgscenter
             display flex
             justify-content: space-between  
</style>
