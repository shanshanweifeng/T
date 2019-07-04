<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">苏州</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>

          <div class="button-wrapper">
            <div class="button">上海</div>
          </div>

          <div class="button-wrapper">
            <div class="button">三亚</div>
          </div>

          <div class="button-wrapper">
            <div class="button">香港</div>
          </div>

          <div class="button-wrapper">
            <div class="button">杭州</div>
          </div>

          <div class="button-wrapper">
            <div class="button">广州</div>
          </div>

          <div class="button-wrapper">
            <div class="button">成都</div>
          </div>

          <div class="button-wrapper">
            <div class="button">深圳</div>
          </div>

          <div class="button-wrapper">
            <div class="button">苏州</div>
          </div>

          <div class="button-wrapper">
            <div class="button">桂林</div>
          </div>

          <div class="button-wrapper">
            <div class="button">西安</div>
          </div>

          <div class="button-wrapper">
            <div class="button">厦门</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">A</div>
        <div class="item-list">
          <div class="item border-bottom">阿坝藏族羌族自治州</div>
          <div class="item border-bottom">阿坝藏族羌族自治州</div>
          <div class="item border-bottom">阿坝藏族羌族自治州</div>
          <div class="item border-bottom">阿坝藏族羌族自治州</div>
          <div class="item border-bottom">阿坝藏族羌族自治州</div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">b</div>
        <div class="item-list">
          <div class="item border-bottom">阿坝藏族羌族自治州</div>
          <div class="item border-bottom">阿坝藏族羌族自治州</div>
          <div class="item border-bottom">阿坝藏族羌族自治州</div>
          <div class="item border-bottom">阿坝藏族羌族自治州</div>
          <div class="item border-bottom">阿坝藏族羌族自治州</div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">c</div>
        <div class="item-list">
          <div class="item border-bottom">阿坝藏族羌族自治州</div>
          <div class="item border-bottom">阿坝藏族羌族自治州</div>
          <div class="item border-bottom">阿坝藏族羌族自治州</div>
          <div class="item border-bottom">阿坝藏族羌族自治州</div>
          <div class="item border-bottom">阿坝藏族羌族自治州</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: "CityList",
  mounted () {
      this.scroll = new Bscroll(this.$refs.wrapper)
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.border-topbottom {
  &:before {
    border-color: #CCC;
  }

  &:after {
    background-color: #CCC;
  }
}

.border-topbottom {
  &:before {
    border-color: #CCC;
  }
}

.list {
  overflow: hidden;
  position: absolute;
  top: 1.58rem;
  left: 0;
  right: 0;
  bottom: 0;

  .title {
    line-height: 0.54rem;
    background: #eee;
    padding-left: 0.2rem;
    color: #666;
  }

  .button-list {
    overflow: hidden;
    padding .1rem .4rem .1rem .1rem;
    // margin: 0 auto;

    .button-wrapper {
      float: left;
      width: 33.33%;

      .button {
        margin: 0.1rem;
        padding: 0.1rem 0;
        text-align: center;
        border-radius: 0.06rem;
        border: 0.02rem solid #ccc;
      }
    }
  }

  .item-list {
    .item {
      line-height: 0.76rem;
      padding-left: 0.2rem;
    }
  }
}
</style>
