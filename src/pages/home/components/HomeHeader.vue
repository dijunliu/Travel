<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe658;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe63c;</span>输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        城市
        <span class="iconfont">&#xe659;</span>
      </div>
    </router-link>
  </div>
</template>
<script>
export default {
  name: "HomeHeader"
};
</script>
<style lang='stylus' scoped>
@import '~style/varibles.styl';

.header {
  line-height: 0.96rem;
  display: flex;
  background: $bgColor;
  color: #fff;

  .header-left {
    float: left;
    width: 0.64rem;
    text-align: center;

    .back-icon {
      text-align: center;
      font-size: 0.4rem;
    }
  }

  .header-right {
    float: rigth;
    width: 1.24rem;
    text-align: center;
    color: #fff;
  }

  .header-input {
    float: rigth;
    width: 1.24rem;
    flex: 1;
    background: #fff;
    border-radius: 4px;
    margin: 8px 0;
    height: 0.67rem;
    line-height: 0.6rem;
    color: #a6a8a9;
    padding-left: 5px;
  }
}
</style>