<template>
  <div class="container">
    <div class="title border-bottom">看了该景点的人还看了</div>
    <div class="detail border-bottom" v-for="(item, index) in recommends" :key="index">
      <div class="img-con">
        <img :src="item.img" alt="">
      </div>
      <div class="detail-center">
        <div class="top">{{item.title}}<span class="level">({{item.level}})</span></div>
        <div class="center">
          <div class="score">
            <star :size=24 :score=item.score></star>
          </div>
          <div class="comments">{{item.totalCommends}}条评论</div>
        </div>
        <div class="bottom">{{item.address}}</div>
      </div>
      <div class="price"><span class="rmb">￥</span><span class="num">{{item.price}}</span>起</div>
    </div>
  </div>
</template>

<script>
import Star from 'common/star/star'
export default {
  components: {
    Star
  },
  props: {
    recommends: {
      type: Array
    }
  },
  name: 'DetailRecommend'
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
  .container
    background #fff
    margin-bottom .2rem
    .title
      position relative
      height .88rem
      line-height .88rem
      padding-left .35rem
      color #333
      font-size .3rem
      &:after
        content: " "
        position: absolute
        top: .3rem
        left: .2rem
        width: .06rem
        height: .25rem
        background: #1ba9ba
    .detail
      padding .2rem
      display flex
      color #9e9e9e
      .img-con
        overflow hidden
        width 1.7rem
        img
          width 100%
      .detail-center
        flex 1
        display flex
        flex-direction column
        justify-content space-between
        padding-left .2rem
        .top
          color #333
          font-size .3rem
          .level
            color #9e9e9e
        .center
          display flex
          margin-bottom: -0.3rem
          .comments
            margin-left .4rem
            font-size .24rem
        .bottom
          font-size .24rem
      .price
        text-align right
        width 1.2rem
        font-size .24rem
        .rmb, .num
          color  #ff9800
        .num
          font-size .36rem
</style>
