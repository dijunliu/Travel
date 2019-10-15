<template>
  <div class="cityList" ref="wrapper">
    <div>
      <div class="current item">
        <div class="item-title">当前城市</div>
        <div class="item-content">
          <span class="item-cell">成都</span>
        </div>
      </div>
      <div class="hot item">
        <div class="item-title">热门城市</div>
        <div class="item-content">
          <span class="item-cell" v-for="city in hotCities" :key="city.id">{{city.name}}</span>
        </div>
      </div>
      <div class="sort item" v-for="(lists,key) in cities" :key="lists.id">
        <div class="item-title">{{key}}</div>
        <ul class="item-lists">
          <li class="item-list" v-for="city in lists" :key="city.id">{{city.name}}</li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
import Bscroll from "better-scroll";
export default {
  name: "CityList",
  props: { cities: Object, hotCities: Array },
  mounted() {
    this.scroll = new Bscroll(this.$refs.wrapper);
  }
};
</script>
<style lang="stylus" scoped>
@import '~style/varibles.styl';

.cityList {
  overflow: hidden;
  position: absolute;
  top: 1.76rem;
  bottom: 0;
  left: 0;
  right: 0;

  .item {
    .item-title {
      background: #eee;
      height: 0.5rem;
      line-height: 0.5rem;
      text-indent: 0.2rem;
    }

    .item-content {
      overflow: hidden;
      margin-bottom: 0.2rem;

      .item-cell {
        padding: 0.1rem 0.7rem;
        border: #333 solid 1px;
        border-radius: 3px;
        margin: 0.2rem 0.2rem;
        float: left;
        margin-bottom: 0;
        margin-right: 0;
      }
    }

    .item-lists {
      .item-list {
        height: 0.6rem;
        line-height: 0.6rem;
        border-bottom: #d0d0d0 solid 1px;
        padding-left: 0.2rem;
      }
    }
  }
}
</style>