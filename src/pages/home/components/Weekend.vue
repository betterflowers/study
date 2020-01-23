<template>
  <div>
    <div class="recommend-title">周末去哪儿</div>
    <ul>
        <li class="item border-bottom" v-for="item of weekendList"
            :key="item.id">
            <div class="item-img-wrapper">
                <img class="item-img" :src="item.imgUrl"/>
            </div>
            <div class="item-info">
                <div class="item-title">{{item.title}}</div>
                <P class="item-desc">{{item.desc}}</P>
            </div>
        </li>
    </ul>
  </div>
</template>

<script>
export default {
    name: 'HomeWeekend',
    props:{
        weekendList: Array
    } 
}
</script>

<style lang="stylus" scoped>
 @import '~styles/varibles.styl'
    .recommend-title
         color: black
         line-height: .7rem
         text-indent: .2rem
         background: #eeeeee
        .item-img-wrapper
            overflow:hidden
            height: 0
            padding-bottom: 37.4375%
            .item-img
              width: 100%
        .item-info
               padding: .14rem .2rem .2rem .2rem
        .item-title
                line-height: .48rem
                font-size: .28rem
                padding-right: 1.4rem
        .item-desc
                line-height: .42rem
                color: #616161
                font-size: .21rem
                padding-right: 1rem
                ellipsis()
</style>