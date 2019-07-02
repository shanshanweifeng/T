<template>
    <div>
        <div class="recommend-title">周末去哪儿</div>
        <ul>
            <li class="item" v-for="item of WeekendList" :key="item.id">
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
    data(){
        return {
            WeekendList:[{
                id:'001',
                imgUrl:"https://imgs.qunarzz.com/sight/source/1505/8a/d412db9fcd44dd.jpg_r_640x214_86f303a2.jpg",
                des1:"苏州必打卡",
                des2:"苏州必须要留下足迹的十个地标"
            },
            {
                id:'002',
                imgUrl:"https://imgs.qunarzz.com/sight/source/1505/70/b2f8425ce486ed.jpg_r_640x214_5db9de57.jpg",
                des1:"细嗅历史的气息",
                des2:"阅尽沧桑，不变的是恬静，待君细细品味"
            },
            {
                id:'003',
                imgUrl:"https://imgs.qunarzz.com/sight/source/1505/3e/18b666031b22e7.jpg_r_640x214_864dce2f.jpg",
                des1:"古典园林逛个够",
                des2:"如果是第一次来苏州，园林是一定要逛的"
            },
            {
                id:'004',
                imgUrl:"https://imgs.qunarzz.com/sight/source/1505/d7/5acd9640ee6cb2.jpg_r_640x214_975d2c3f.jpg",
                des1:"情侣必游",
                des2:"浪漫的乐园、静宜的园林，每一处，都弥漫这江南小镇委婉温馨的气息……"
            },
            {
                id:'005',
                imgUrl:"https://imgs.qunarzz.com/sight/source/1507/ab/1c456b9cbffc31.jpg_r_640x214_1c2552de.jpg",
                des1:"魅力江南古镇",
                des2:"发呆静思，度过一个悠闲的下午"
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
