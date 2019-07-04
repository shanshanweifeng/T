<template>
    <div class="search">
        <input class="search-input" type="text" placeholder="输入城市名或拼音">
    </div>
</template>

<script>
export default {
    name: 'CitySearch'
}
</script>

<style lang="stylus" scoped>
    @import '~styles/varibles.styl'
        .search
            height .72rem
            padding 0 .1rem
            background $bgColor
            // background pink
            .search-input
                width 100%
                height .62rem
                color #616161
                text-align center
                border-radius .06rem
                padding 0 .1rem
                box-sizing border-box
</style>
