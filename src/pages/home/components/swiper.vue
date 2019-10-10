<template>
  <swiper :options="swiperOption">
    <!-- slides -->
    <swiper-slide v-for="swiper of swiperList" :key="swiper.id">
      <img class="swiper-img" :src="swiper.imgUrl" />
    </swiper-slide>
    <!-- Optional controls -->
    <div class="swiper-pagination" slot="pagination"></div>
  </swiper>
</template>
<script>
export default {
  name: "HomeSwiper",
  data: function() {
    return {
      swiperOption: {
        pagination: ".swiper-pagination",
        loop: true
      }
    };
  },
  props: { swiperList: Array }
};
</script>
<style lang="stylus" scoped>
>>> .swiper-pagination-bullet-active {
  background: #fff;
}

.swiper-img {
  width: 100%;
}
</style>