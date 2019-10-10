<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page,index) in pages" :key="index">
        <div class="icon" v-for="icon in page" :key="icon.id">
          <div class="icon-img">
            <img :src="icon.imgUrl" />
          </div>
          <p class="icon-desc">{{icon.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>
<script>
export default {
  name: "HomeIcons",
  data() {
    return {
      swiperOption: { autoplay: false }
    };
  },
  props: {
    iconList: Array
  },
  computed: {
    pages() {
      const pages = [];
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8);
        if (!pages[page]) {
          pages[page] = [];
        }
        pages[page].push(item);
      });
      return pages;
    }
  }
};
</script>
<style lang="stylus" scoped>
@import '~style/varibles.styl';
@import '~style/mixins.styl';

.icons >>> .swiper-slide {
  padding-bottom: 50%;
  height: 0;
}

.icon {
  height: 0;
  overflow: hidden;
  position: relative;
  float: left;
  width: 25%;
  padding-bottom: 25%;

  .icon-img {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0.24rem;
    padding: 0.28rem;

    img {
      height: 100%;
      display: block;
      margin: 0 auto;
    }
  }

  .icon-desc {
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    text-align: center;
    height: 0.28rem;
    line-height: 0.28rem;
    color: $darkTextColor;
    ellipsis();
  }
}
</style>