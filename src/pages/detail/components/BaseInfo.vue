<template>
  <section class="detail">
    <div class="detail-info">
      <div class="detail-item border-right">
        <div class="item-info">
          <p class="top-score">
            <span class="score">{{info.score}}</span>分
            <span>{{info.scoreDes}}</span>
          </p>
          <p class="bottom">
            <span>{{info.commonCount}}条评论</span>
            <span>{{info.ideaCount}}条攻略</span>
          </p>
        </div>
        <div class="iconfont item-icon">&#xe62e;</div>
      </div>
      <div class="detail-item">
        <div class="item-info">
          <p class="top">景点简介</p>
          <p class="bottom">开放时间、贴士</p>
        </div>
        <div class="iconfont item-icon">&#xe62e;</div>
      </div>
    </div>
    <div class="detail-address">
      <span class="iconfont item-icon">&#xe63f;</span>
      <span class="address">{{info.address}}</span>
      <span class="iconfont item-icon">&#xe62e;</span>
    </div>
  </section>
</template>

<script>
export default {
  name: 'BaseInfo',
  props: {
    info: {
      type: Object
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
  .detail
    background #fff
    display flex
    flex-direction column
    border-radius: .2rem .2rem 0 0
    padding .2rem .2rem 0 .2rem
    margin-top -0.1rem
    margin-bottom .2rem
    .detail-info
      display flex
      .detail-item
        display flex
        justify-content space-between
        width 50%
        box-sizing border-box
        padding-right .1rem
        .top-score
          color #ff8201
          .score
            font-size .44rem
        .item-icon
          line-height .8rem
          color #aaaaaa
        .item-info
          display inline-block
          height .8rem
          line-height .4rem
          padding .1rem
          .bottom
            color #a3a3a3
            font-size .24rem
    .detail-address
      display inline-flex
      height .8rem
      line-height .8rem
      font-size .28rem
      padding-left .2rem
      padding-right .1rem
      justify-content space-between
      .address
        display inline-block
        ellipsis()
      .item-icon
        color #aaaaaa
</style>
