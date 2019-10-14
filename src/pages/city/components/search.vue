<template>
  <div class="citySearch">
    <input type="text" placeholder="输入城市名或拼音" />
  </div>
</template>
<script>
export default { name: "CitySearch" };
</script>
<style lang="stylus" scoped>
@import '~style/varibles.styl';

.citySearch {
  background: $bgColor;
  height: 0.8rem;

  input {
    margin: 0 auto;
    width: 94%;
    display: block;
    height: 0.65rem;
    border-radius: 4px;
    text-align: center;
  }
}
</style>