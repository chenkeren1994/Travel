<template>
    <div>
      <div class="title">热销推荐</div>
      <ul>
        <li v-for="item in list" :key="item.id" class="item border-bottom">
          <img class="item-img" :src="item.imgUrl" :alt="item.title">
          <div class="item-info">
            <p class="item-title">{{item.title}}</p>
            <p class="item-desc">{{item.desc}}</p>
            <button class="item-button">查看详情</button>
          </div>
        </li>
      </ul>
    </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.title
  background #eee
  line-height .8rem
  margin-top .2rem
  text-indent .2rem
.item
  display flex
  height 1.9rem
  overflow hidden
  .item-img
    width 1.7rem
    height 1.7rem
    padding .1rem
  .item-info
    flex 1
    padding .1rem
    min-width 0
    .item-title
      line-height .54rem
      font-size .32rem
    .item-desc
      line-height .4rem
      color #ccc
    .item-button
      line-height .44rem
      margin-top .26rem
      color #fff
      background #ff9300
      padding 0 .2rem
      border-radius .06rem
      ellipsis()
</style>
