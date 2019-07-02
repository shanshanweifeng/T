<template>
    <div>
        <div class="recommend-title">热销推荐</div>
        <ul>
            <li class="item border-bottom" v-for="item of RecommendList" :key="item.id">
                <img class="item-img" :src="item.imgUrl" alt="">
                <div class="img-info">
                    <p class="img-title">{{item.des1}}</p>
                    <p class="img-des">{{item.des2}}</p>
                    <div class="button-info">
                        <button class="title-button">查看详情</button>
                        <span class="title-place">{{item.des3}}</span>
                    </div>
                </div>
            </li>
        </ul>
    </div>    
</template>

<script>
export default {
    name: 'HomeRecommend',
    data(){
        return {
            RecommendList:[{
                id:'001',
                imgUrl:"https://imgs.qunarzz.com/sight/p0/201405/14/3dfad2bcd30c40e91a15f8b7296d86a6.jpg_200x200_265db173.jpg",
                des1:"同里古镇",
                des2:"13382条评论",
                des3:"吴江市"
            },
            {
                id:'002',
                imgUrl:"https://imgs.qunarzz.com/sight/p0/1903/61/617ac4a711f6cb34a3.img.jpg_200x200_5e8ac1c0.jpg",
                des1:"苏州乐园森林水世界",
                des2:"2950条评论",
                des3:"苏州乐园"
            },
            {
                id:'003',
                imgUrl:"https://imgs.qunarzz.com/tuan/team2/1507/49/40f46fd83f4ae7.jpg_200x200_7a0a0674.jpg",
                des1:"白马涧",
                des2:"2076条评论",
                des3:"高新区"
            },
            {
                id:'004',
                imgUrl:"https://imgs.qunarzz.com/sight/p0/201301/14/bf26ff3662c7a2a393835fbb.png_200x200_35c6466e.png",
                des1:"苏州海洋馆",
                des2:"616评论",
                des3:"吴中区"
            }]
        }
    }
}
</script>

<style lang="stylus" scoped>
    @import '~styles/mixins.styl';
    .recommend-title
        margin-top .2rem
        line-height .8rem
        background-color #eee
        text-indent .2rem
    .item
        overflow hidden
        display flex
        height 1.9rem
        .item-img
            width 1.7rem
            height 1.7rem
            padding .1rem
        .img-info
            flex 1
            // margin-top .1rem
            padding .1rem
            .img-title
                color #212121
                font-size .32rem
                line-height .54rem
                ellipsis()
            .img-des
                line-height .4rem
                color #616161
            .button-info
                position relative
                margin-top .1rem    
                .title-button
                    background-color  #ff9300
                    border-radius .13rem
                    padding 0 .1rem
                .title-place
                    position absolute
                    right .1rem
                    bottom 0
                    color #616161
                    font-size .24rem
</style>
