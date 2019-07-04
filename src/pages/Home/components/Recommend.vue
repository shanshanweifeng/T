<template>
    <div>
        <div class="recommend-title">热销推荐</div>
        <ul>
            <li class="item border-bottom" v-for="item of list" :key="item.id">
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
    props: {
        list:Array
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
