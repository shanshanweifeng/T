<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide  v-for="item of swiperList" :key="item.id">
        <img
          class="swiper-img"
          :src="item.imgUrl" 
        />
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  data() {
    return {
      swiperOption: {
          pagination: '.swiper-pagination',
          loop: true,
          autoplay:3000
      },
      swiperList:[{
          id:'001',
          imgUrl:"https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20196/a5d26ebec399b3aef013f45771ae96f0.jpg_750x200_de947eef.jpg"
      },
      {
          id:'002',
          imgUrl:"https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20195/5eb82a8ca5b0cebb2c3ae1a53a4d8f81.jpg_750x200_645bfba1.jpg"
      },
      {
          id:'003',
          imgUrl:"https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20196/b421363bbbb9184deacb4247eeea7485.jpg_750x200_12b42643.jpg"
      },
      {
          id:'004',
          imgUrl:"https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/ca802b4ac8b7aaff977159253abbacb4.jpg_750x200_b2400809.jpg"
      },
      {
          id:'005',
          imgUrl:"https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/87a224d0349d94a11e97f31aa1aba4f5.jpg_750x200_1f78af87.jpg"
      },
      {
          id:'006',
          imgUrl:"https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20196/818f6cc784ae6669b74bbbb255414a53.jpg_750x200_66ca5873.jpg"
      },
      {
          id:'007',
          imgUrl:"https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20197/6a01f2ec2db0be95abcc95d343823268.jpg_750x200_fe7e8b72.jpg"
      },
      {
          id:'008',
          imgUrl:"https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/b1847cf91a34cf95402240a3f62aad77.jpg_750x200_26ea3527.jpg"
      },
      {
          id:'009',
          imgUrl:"https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20197/1f69b3ab28f9962158c798a8a3f5b4b3.jpg_750x200_fb4bf7c4.jpg"
      },
      {
          id:'010',
          imgUrl:"https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20196/63ebd4128233893a52472115065a3c23.jpg_750x200_af32b5ef.jpg"
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active
    background-color  #fff
.wrapper
    overflow hidden
    width 100%
    height 0
    padding-bottom 26.66%
    .swiper-img 
        width: 100%;
</style>

