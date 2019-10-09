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
      },
      swiperList: [
        {
          id: "001",
          imgUrl:
            "//m.360buyimg.com/mobilecms/s700x280_jfs/t1/64525/13/11604/98387/5d8d828dE0c5ed64d/a62d0d8bc8817724.jpg!cr_1125x445_0_171!q70.jpg.dpg"
        },
        {
          id: "002",
          imgUrl:
            "//m.360buyimg.com/mobilecms/s700x280_jfs/t1/48636/9/11841/72032/5d89e3ccE93c93c41/c01fef6b44d43bf5.jpg!cr_1125x445_0_171!q70.jpg.dpg"
        },
        {
          id: "003",
          imgUrl:
            "//m.360buyimg.com/mobilecms/s700x280_jfs/t1/48636/9/11841/72032/5d89e3ccE93c93c41/c01fef6b44d43bf5.jpg!cr_1125x445_0_171!q70.jpg.dpg"
        },
        {
          id: "004",
          imgUrl:
            "//m.360buyimg.com/mobilecms/s700x280_jfs/t1/31162/17/1128/101786/5c46ead8E22ee9740/f66061da227c1965.jpg!cr_1125x445_0_171!q70.jpg.dpg"
        }
      ]
    };
  }
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