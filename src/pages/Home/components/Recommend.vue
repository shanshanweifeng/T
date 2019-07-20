<template>
  <div>
    <div class="recommend-title">热销推荐</div>
    <ul>
        <router-link tag="li" class="item border-bottom" v-for="item of list" :key="item.id" :to="'/detail/' + item.id">
          <img class="item-img" :src="item.imgUrl" alt />
          <div class="img-info">
            <p class="img-title">{{item.des1}}</p>
            <p class="img-des">{{item.des2}}</p>
            <div class="button-info">
              <button class="title-button">查看详情</button>
              <span class="title-place">{{item.des3}}</span>
            </div>
          </div>
        </router-link>  
    </ul>
  </div>
</template>

<script>
export default {
  name: "HomeRecommend",
  props: {
    list: Array
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl';

.recommend-title {
  margin-top: 0.2rem;
  line-height: 0.8rem;
  background-color: #eee;
  text-indent: 0.2rem;
}

.item {
  overflow: hidden;
  display: flex;
  height: 1.9rem;

  .item-img {
    width: 1.7rem;
    height: 1.7rem;
    padding: 0.1rem;
  }

  .img-info {
    flex: 1;
    // margin-top .1rem
    padding: 0.1rem;

    .img-title {
      color: #212121;
      font-size: 0.32rem;
      line-height: 0.54rem;
      ellipsis();
    }

    .img-des {
      line-height: 0.4rem;
      color: #616161;
    }

    .button-info {
      position: relative;
      margin-top: 0.1rem;

      .title-button {
        background-color: #ff9300;
        border-radius: 0.13rem;
        padding: 0 0.1rem;
      }

      .title-place {
        position: absolute;
        right: 0.1rem;
        bottom: 0;
        color: #616161;
        font-size: 0.24rem;
      }
    }
  }
}
</style>
