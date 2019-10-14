<template>
  <ul class="alp-items">
    <li class="alp-item" v-for="(citie,key) in cities" :key="citie.id">{{key}}</li>
  </ul>
</template>
<script>
export default {
  name: "CityAlphabet",
  props: {
    cities: Object
  }
};
</script>
<style lang="stylus" scoped>
@import '~style/varibles.styl';

.alp-items {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 0.4rem;

  .alp-item {
    color: $bgColor;
    text-align: center;
    line-height: 0.4rem;
  }
}
</style>