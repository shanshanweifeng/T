<template>
  <ul class="list">
    <li class="item" 
      v-for="(item,key) of cities" 
      :key="key" 
      @click="handClick">
      {{key}}
      </li>
  </ul>
</template>

<script>
export default {
  name: "CityAlphabet",
  props: {
    cities: Object
  },
  methods:{
    handClick (e) {
      this.$emit('letter-change',e.target.innerText)
    }
  }
};
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.list 
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: absolute;
  right: 0.07rem;
  top: 1.58rem;
  bottom: 0;
  width: 0.4rem;
  .item 
    line-height: 0.35rem;
    text-align: center;
    color: $bgColor;
</style>
