<template>
    <div class="header">
        <div class="header-left"><div class="iconfont back-icon">&#xe624;</div></div>
        <div class="header-input"><span class="iconfont">&#xe632;</span>请输入城市/景点/游玩主题</div>
        <router-link to="/City">
			<div class="header-right" >
				{{this.$store.state.city}}
				<span class="iconfont arrow-icon">&#xe64a;</span>
			</div>
		</router-link>
    </div>
</template>

<script>
export default {
	name:  'HomeHeader'
}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.header
		display flex
		height 0.86rem
		line-height 0.86rem
		background $bgColor
		color #fff
		.header-left
			width .64rem
			float left
			.back-icon
				text-align center
				font-size .37rem
		.header-input
			flex 1
			height .64rem
			line-height .64rem
			margin-left .2rem
			margin-top .12rem
			padding-left .2rem
			color #cccccc
			background #fff
			border-radius .1rem
		.header-right
			min-width 1.04rem
			padding 0 .1rem
			float right
			color #fff
			text-align center
			.arrow-icon
				font-size .24rem
				margin-left .04rem
</style>

