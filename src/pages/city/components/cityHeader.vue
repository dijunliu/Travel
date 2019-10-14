<template>
  <div class="cityHeader">
    城市选择
    <router-link to="/">
      <div class="iconfont returnBack">&#xe658;</div>
    </router-link>
  </div>
</template>
<script>
export default { name: "CityHeader" };
</script>
<style lang="stylus" scoped>
@import '~style/varibles.styl';

.cityHeader {
  background: #f9f;
  text-align: center;
  height: 0.96rem;
  line-height: 0.96rem;
  background: $bgColor;
  color: #fff;

  .returnBack {
    position: absolute;
    top: 0;
    left: 0.2rem;
    font-size: 0.5rem;
    color: #fff;
  }
}
</style>