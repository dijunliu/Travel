<template>
  <div class="weenkend">
    <div class="weenkend-title">周末推荐</div>
    <ul class="weenkend-lists">
      <li class="weenkend-list" v-for="weekend in weekendList" :key="weekend.id">
        <div class="weenkend-item">
          <img :src="weekend.imgUrl" />
          <div class="item-content">
            <p class="item-title">{{weekend.title}}</p>
            <p class="item-desc">{{weekend.desc}}</p>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default { name: "HomeWeekend", props: { weekendList: Array } };
</script>
<style lang="stylus" scoped>
@import '~style/mixins.styl';

.weenkend-title {
  background: #eee;
  line-height: 0.8rem;
  text-indent: 0.4rem;
  margin-top: 0.2rem;
}

.weenkend-list {
  height: 0;
  padding-bottom: 55%;
  position: relative;
  border-bottom: 1px solid #c5c5c5;
  border-radius: 5px;
  overflow: hidden;
  margin: 0.1rem 0.2rem;
  box-shadow: 1px 2px 4px 1px #8a8a8a;
  border: 1px solid #ffffff;

  .weenkend-item {
    fullDiv();

    img {
      width: 100%;
      box-sizing: border-box;
    }

    .item-content {
      padding: 0.2rem;

      .item-title {
        font-size: 0.3rem;
        font-weight: 600;
      }

      .item-desc {
        color: #949494;
        font-size: 0.3rem;
        margin: 0.15rem 0;
      }
    }
  }
}
</style>