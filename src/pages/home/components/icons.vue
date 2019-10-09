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
      iconList: [
        {
          id: "0001",
          imgUrl:
            "//m.360buyimg.com/mobilecms/s120x120_jfs/t1/20983/16/10753/6124/5c8a16aaE5d6b15d7/01e0e818a7505267.png",
          desc: "京东超市"
        },
        {
          id: "0002",
          imgUrl:
            "//m.360buyimg.com/mobilecms/s120x120_jfs/t1/17169/3/4127/4611/5c2f35cfEd87b0dd5/65c0cdc1362635fc.png.webp",
          desc: "京东超市"
        },
        {
          id: "0003",
          imgUrl:
            "//m.360buyimg.com/mobilecms/s120x120_jfs/t1/20983/16/10753/6124/5c8a16aaE5d6b15d7/01e0e818a7505267.png",
          desc: "京东超市"
        },
        {
          id: "0004",
          imgUrl:
            "//m.360buyimg.com/mobilecms/s120x120_jfs/t1/20983/16/10753/6124/5c8a16aaE5d6b15d7/01e0e818a7505267.png",
          desc: "京东超市"
        },
        {
          id: "0005",
          imgUrl:
            "//m.360buyimg.com/mobilecms/s120x120_jfs/t1/22262/9/1470/4527/5c120cd0E5d3c6c66/4792ec307a853e9f.png.webp",
          desc: "京东超市"
        },
        {
          id: "0006",
          imgUrl:
            "//m.360buyimg.com/mobilecms/s120x120_jfs/t18454/342/2607665324/6406/273daced/5b03b74eN3541598d.png.webp",
          desc: "京东超市"
        },
        {
          id: "0007",
          imgUrl:
            "//m.360buyimg.com/mobilecms/s120x120_jfs/t18454/342/2607665324/6406/273daced/5b03b74eN3541598d.png.webp",
          desc: "京东超市"
        },
        {
          id: "0008",
          imgUrl:
            "//m.360buyimg.com/mobilecms/s120x120_jfs/t16828/63/2653634926/5662/d18f6fa1/5b03b779N5c0b196f.png.webp",
          desc: "京东超市"
        },
        {
          id: "0006",
          imgUrl:
            "//m.360buyimg.com/mobilecms/s120x120_jfs/t1/20983/16/10753/6124/5c8a16aaE5d6b15d7/01e0e818a7505267.png",
          desc: "京东超市"
        },
        {
          id: "0007",
          imgUrl:
            "//m.360buyimg.com/mobilecms/s120x120_jfs/t1/20983/16/10753/6124/5c8a16aaE5d6b15d7/01e0e818a7505267.png",
          desc: "京东超市"
        },
        {
          id: "0008",
          imgUrl:
            "//m.360buyimg.com/mobilecms/s120x120_jfs/t1/20983/16/10753/6124/5c8a16aaE5d6b15d7/01e0e818a7505267.png",
          desc: "京东超市"
        }
      ],
      swiperOption: { autoplay: false }
    };
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
    height: 0.24rem;
    line-height: 0.24rem;
    color: $darkTextColor;
    ellipsis();
  }
}
</style>