<template>
  <div>
    <div class="iconfont">&#xe85c;<span class="recommend-title"> 猜你喜欢</span></div>
    <ul>
      <router-link tag='li'
                   class="item border-bottom"
                   v-for="item of recommendList"
                   :key="item.id"
                   :to="'/detail/' + item.id">
        <div class="item-img-wrapper">
          <img class="item-img"
               :src="item.imgUrl" />
        </div>
        <div class="item-info">
          <div class="item-title">{{item.title}}</div>
          <P class="item-desc">{{item.desc}}</P>
          <button class="item-button">查看详情</button>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    recommendList: Array
  }

}
</script>

<style lang="stylus" scoped>
.iconfont {
  color: red;
  background: #eeeeee;
  margin-top: 0.2rem;
  line-height: 0.8rem;
  text-indent: 0.2rem;
}

.recommend-title {
  color: black;
  font-weight: bolder;
}

.item {
  overflow: hidden;
  display: flex;
  height: 2rem;
  position: relative;

  .item-img {
    width: 1.7rem;
    height: 1.7rem;
    padding: 0.1rem;
  }

  .item-info {
    flex: 1;
    padding: 0.1rem;
  }

  .item-title {
    line-height: 0.54rem;
    font-size: 0.32rem;
    margin-top: 0.1rem;
  }

  .item-desc {
    line-height: 0.4rem;
    color: #ccc;
  }

  .item-button {
    position: absolute;
    border-radius: 0.15rem;
    width: 1.7rem;
    right: 0.3rem;
    bottom: 0.2rem;
    background: #ff9300;
    color: #fff;
  }
}
</style>