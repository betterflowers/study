<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page,index) of pages"
                    :key="index">
        <div class="icon"
             v-for="item of page"
             :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content"
                 :src="item.imgSrc">
          </div>
          <p class="icon-desc">{{item.content}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    List: Array
  },
  data () {
    return {
      swiperOption: {
        autoplay: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.List.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages;
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.icons >>> .swiper-container {
  height: 0;
  padding-bottom: 45%;

  .icon {
    position: relative;
    overflow: hidden;
    float: left;
    width: 25%;
    height: 0;
    padding-bottom: 22.5%;
    background: white;

    .icon-img {
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0.41rem;
      box-sizing: border-border-box;
      padding: 0.1rem;
      background: white;

      .icon-img-content {
        display: block;
        margin: 0 auto;
        height: 100%;
      }
    }

    .icon-desc {
      position: absolute;
      left: 0;
      right: 0;
      bottom: 0;
      height: 0.41rem;
      line-height: 0.41rem;
      text-align: center;
      color: $darkTextColor;
    }
  }
}
</style>