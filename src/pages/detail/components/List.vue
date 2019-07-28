<template>
  <div class="list">
    <div class="item" v-for="(item,index) of list" :key="index">
      <div class="item-title border-bottom">
        <span class="item-title-icon"></span>
        {{item.title}}
        <div class="item-children" v-if="item.children">
          <Detaillist :list="item.children"></Detaillist>
        </div>
      </div>
    </div>
    <!-- <div class="xiala">
      查看剩余产品
      <span class="iconfont arrow-icon">&#xe64a;</span>
    </div> -->
  </div>
</template>

<script>
export default {
  name: "Detaillist",
  props: {
    list: Array
  }
};
</script>

<style lang="stylus" scoped>

  .item-title {
    line-height: 0.8rem;
    font-size: 0.32rem;
    padding: 0 0.2rem;

    .item-title-icon {
      position: relative;
      left: 0.06rem;
      top: 0.07rem;
      display: inline-block;
      // position: absolute;
      width: 0.36rem;
      height: 0.36rem;
      background: url('http://s.qunarzz.com/piao/image/touch/sight/detail.png') 0 -0.45rem no-repeat; // s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat;
      margin-right: 0.1rem;
      background-size: 0.4rem 3rem;
    }

    .item-children {
      padding: 0 0.2rem;
    }

    .xiala {
      text-align: center;
      color: #616161;
      font-size: 14px;
    }

    .arrow-icon {
      font-size: 12px;
    }
  }

</style>
