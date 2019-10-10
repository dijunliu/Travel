<template>
  <div class="recommend">
    <div class="recommend-title">热门推荐</div>
    <ul class="recommend-lists">
      <li class="recommend-list" v-for="recommend in recommendList" :key="recommend.id">
        <div class="recommend-item">
          <img :src="recommend.imgUrl" />
          <div class="r-i-content">
            <p class="r-i-title">{{recommend.title}}</p>
            <p class="r-i-desc">{{recommend.desc}}</p>
            <p class="r-i-amount">
              <span class="r-i-money">￥99</span> 起
            </p>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default { name: "HomeRecommend", props: { recommendList: Array } };
</script>
<style lang="stylus" scoped>
@import '~style/mixins.styl';

.recommend-title {
  background: #eee;
  line-height: 0.8rem;
  text-indent: 0.4rem;
  margin-top: 0.2rem;
  margin-top: 0.2rem;
}

.recommend-list {
  height: 0;
  padding-bottom: 25%;
  position: relative;
  border-bottom: 1px solid #c5c5c5;

  .recommend-item {
    fullDiv();

    img {
      height: 100%;
      float: left;
      padding: 0.15rem;
      box-sizing: border-box;
    }

    .r-i-content {
      float: left;
      height: 100%;
      padding: 0.2rem;
      box-sizing: border-box;
      width: 71%;

      .r-i-title {
        font-size: 0.3rem;
        font-weight: 600;
      }

      .r-i-desc {
        color: #949494;
        font-size: 0.3rem;
        margin: 0.15rem 0;
        ellipsis();
      }

      .r-i-amount {
        color: #949494;

        .r-i-money {
          ellipsis();
          color: #FF9800;
          font-size: 0.4rem;
          font-weight: 600;
        }
      }
    }
  }
}
</style>