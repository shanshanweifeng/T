<template>
    <div class="header">
        <router-link to="/">
            <div class="iconfont city-back">&#xe624;</div>
        </router-link>
        城市选择
    </div>    
</template>

<script>
export default {
    name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
    @import '~styles/varibles.styl'
    .header
        position relative
        overflow hidden
        height .86rem
        line-height  .86rem
        text-align center
        color #fff
        background $bgColor
        font-size .3rem
        .city-back
            position absolute
            left 0
            top 0
            width .8rem
            text-align center
            font-size .33rem
            color #fff
</style>
