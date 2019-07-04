<template>
    <div>
        <div class="recommend-title">周末去哪儿</div>
        <ul>
            <li class="item" v-for="item of list" :key="item.id">
                <div class="item-imgwrapper">
                    <img class="item-img" :src="item.imgUrl">
                </div>
                <div class="img-info">
                    <p class="img-title">{{item.des1}}</p>
                    <p class="img-des">{{item.des2}}</p>
                </div>
                <div class="fill-up"></div>
            </li>
        </ul>
    </div>    
</template>

<script>
export default {
    name: 'HomeWeekend',
    props: {
        list: Array
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
        width 100%
        overflow hidden
        // margin-bottom .1rem
        .item-imgwrapper
            height 0
            padding-bottom 37.4375%
            .item-img
                width 100%
        .img-info
            position relative
            padding-top: 0.14rem;
            padding-right: 0.2rem;
            padding-bottom: 0.2rem;
            padding-left: 0.2rem;
            .img-title
                color #212121
                font-size .28rem
                line-height .48rem
                ellipsis()
            .img-des
                font-size .24rem
                line-height .42rem
                color #616161
                ellipsis()   
        .fill-up
            background-color #eee
            height .1rem
</style>
