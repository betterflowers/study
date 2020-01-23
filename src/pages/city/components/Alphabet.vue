<template>
  <ul class="list">
    <li class="item"
        v-for="(item,key) of cities"
        :key="key"
        :ref="key"
        @click="handleLetterClick">{{key}}</li>
  </ul>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  },
  methods: {
    handleLetterClick (e) {
      this.$emit('change', e.target.innerText)
    }

  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.list {
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: absolute;
  right: 0;
  top: 1.78rem;
  bottom: 0;
  width: 0.35rem;
}

.item {
  line-height: 0.4rem;
  text-align: center;
  color: $bgColor;
}
</style>