<template>
  <div>
    <bannerimg></bannerimg>
    <Detailheader></Detailheader>
    <div class="content"></div>
  </div>
</template>

<script>
import bannerimg from "./components/banner.vue";
import Detailheader from "./components/Detailheader.vue";
export default {
  name: "Detail",
  components: {
    bannerimg,
    Detailheader
  }
};
</script>

<style lang="stylus" scoped>
  .content
    height 50rem
</style>
