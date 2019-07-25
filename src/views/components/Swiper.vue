<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img :src="item.imgUrl">
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      //  下面的切换圆圈
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'https://ss0.bdstatic.com/-0U0bnSm1A5BphGlnYG/tam-ogel/19838a56209d42a75fb8b4f16b1d784e_255_144.jpg'
      }, {
        id: '0002',
        imgUrl: 'https://ss0.bdstatic.com/-0U0bnSm1A5BphGlnYG/tam-ogel/c0fe6d397c00f43117e5962881b6f178_255_144.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
    .wrapper >>> .swiper-pagination-bullet-active
      background: white
    .wrapper
      background: #ccc
      overflow hidden
      width: 100%
      height: 0
      padding-bottom:31.25%
    .swiper-slide
      img
        width: 100%
        height: 2.34rem
</style>
