<template>
  <div class="header">城市选择
    <router-link to="/">
      <div class="iconfont header-back">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.header {
  pisition: relative;
  overflow: hidden;
  heigt: $headerHeight;
  line-height: $headerHeight;
  color: #fff;
  text-align: center;
  font-size: 0.32rem;
  background: $bgColor;
}

.header-back {
  position: absolute;
  top: 0;
  left: 0;
  width: 0.64rem;
  text-align: center;
  font-size: 0.4rem;
  color: #fff;
}
</style>