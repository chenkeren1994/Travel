<template>
  <div class="contain">
    <div class="item" v-for="(item, index) of list" :key="index">
      <div class="item-title border-bottom">
        <span class="item-title-icon"></span>
        {{item.title}}
      </div>
      <div v-show="item.children" v-for="(subitem,index) in item.children" :key="index" class="item-info border-bottom">
        <div class="item-desc">
          {{subitem.title}}
        </div>
        <div class="item-price">
          <span class="rmb">￥</span>
          <span class="price">{{subitem.price}}</span>
          <span>起</span><span class="iconfont item-icon">&#xe62d;</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    list: {
      type: Array
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.contain
  margin-bottom .2rem
  background #fff
  .item-title-icon
    position relative
    left .06rem
    top .06rem
    display: inline-block
    width: .36rem
    height: .36rem
    background: url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat
    margin-right: .1rem
    background-size: .4rem 3rem
  .item-title
    line-height .8rem
    font-size .32rem
    padding 0 .2rem
  .item-info
    padding .2rem
    display flex
    justify-content space-between
    align-items center
    min-height .48rem
    color: #333;
    font-size: .3rem;
    .item-desc
      line-height .48rem
      flex-wrap wrap
      flex 1
      display: -webkit-box;
      -webkit-box-orient: vertical;
      -webkit-line-clamp: 2;
      overflow: hidden;
    .item-price
      width 2rem
      color #b5b5b5
      font-size .2rem
      display inline-flex
      justify-content flex-end
      align-items flex-end
      margin-right .2rem
      .rmb, .price
        color #ff9800
      .price
        font-size .4rem
      .item-icon
        font-size 0.25rem
</style>
