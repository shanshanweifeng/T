<template>
    <div class="icons">
        <swiper :options="swiperOption">
        <swiper-slide v-for="(a,index) of pages" :key="index">
        <div class="icon" v-for="item of a" :key="item.id">
            <div class="icon-img"><img class="icon-imgcontent" :src='item.imgUrl'></div>
            <p class="icon-main">{{item.des}}</p>
        </div>
        </swiper-slide>
        </swiper>
    </div>
</template>

<script>
export default {
    name: 'HomeIcons',
    data(){
        return{
        swiperOption: {
            loop: false,
            autoplay:false
      },
        iconList:[{
            id:'001',
            des:'景点门票',
            imgUrl:"https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png"
        },
        {
            id:'002',
            des:'古镇',
            imgUrl:"https://imgs.qunarzz.com/piao/fusion/1803/67/9a1678221b8e0e02.png"
        },
        {
            id:'003',
            des:'亲子游',
            imgUrl:"https://imgs.qunarzz.com/piao/fusion/1803/50/26ffa31b56646402.png"
        },
        {
            id:'004',
            des:'苏州园林',
            imgUrl:"https://imgs.qunarzz.com/piao/fusion/1803/17/99402a22ce4af302.png"
        },
        {
            id:'005',
            des:'寒山寺',
            imgUrl:"https://imgs.qunarzz.com/piao/fusion/1803/fa/2548667cb6e902.png"
        },{
            id:'006',
            des:'华谊兄弟',
            imgUrl:"https://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png"
        },{
            id:'007',
            des:'狮子林',
            imgUrl:"https://imgs.qunarzz.com/piao/fusion/1803/90/59a2f523ee2f9202.png"
        },{
            id:'008',
            des:'拙政园',
            imgUrl:"https://imgs.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png"
        },{
            id:'009',
            des:'虎丘',
            imgUrl:"https://imgs.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png"
        },{
            id:'010',
            des:'上方山',
            imgUrl:"https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/ac9ef584416467d8cc557aad650959fd.png"
        }]
        }
    },
        computed: {
            pages(){
                const pages = [];
                this.iconList.forEach((item,index)=>{
                    const page = Math.floor(index/8)
                    if(!pages[page]){
                        pages[page] = []
                    }
                    pages[page].push(item)
                })
                return pages;
            }
        }
}
</script>

<style lang="stylus" scoped>
    @import '~styles/varibles.styl';
    @import '~styles/mixins.styl';
    .icons >>> .swiper-container
        overflow hidden
        height 0
        padding-bottom 50%
    .icons
        margin-top .1rem    
        .icon
            position relative
            overflow hidden
            float left
            width 25%
            height 0px
            padding-bottom 25%
            .icon-img
                position absolute
                top 0
                left 0
                right 0
                bottom .44rem
                box-sizing border-box
                padding .1rem
                .icon-imgcontent
                    height 100%
                    display block
                    margin 0 auto
            .icon-main
                position absolute
                left 0
                right 0
                bottom 0
                color $bgColorText
                height .44rem
                line-height .44rem
                text-align center
                ellipsis()          
</style>
