<template>
  <section class="container">
    <div class="con-header border-bottom">用户评论</div>
    <div v-for="item in commends" :key="item.id" class="content border-bottom">
      <div class="content-title">
        <div class="start">
          <star :size=24 :score=item.score></star>
        </div>
        <div class="message">
          <span>{{item.name}}</span>&nbsp; <span>{{item.time}}</span>
        </div>
      </div>
      <div class="content-desc">
        <p>{{item.content.desc}}</p>
      </div>
      <div class="content-img" @click="handleContentImgClick(item.id)">
        <div class="img-wraper" v-for="(img, index) in item.content.img" :key="index" v-if="index < 6">
          <img :src=img alt="">
        </div>
        <span class="img-tag">共{{item.content.img.length}}张</span>
      </div>
    </div>
    <!-- <fade-animation>
        <common-galary :refs="common" @close="handleGallaryClose" v-show="showGallary" :imgs="item.content.img"></common-galary>
    </fade-animation> -->
    <div class="content-footer">
      查看全部评论<span class="iconfont">&#xe62e;</span>
    </div>
  </section>
</template>

<script>
import Star from 'common/star/star'
import CommonGalary from 'common/gallary/Gallary'
import FadeAnimation from 'common/fade/FadeAnimation'
export default {
  name: 'UserCommend',
  props: {
    commends: {
      type: Array
    }
  },
  data () {
    return {
      showGallary: false
    }
  },
  components: {
    Star,
    CommonGalary,
    FadeAnimation
  },
  methods: {
    handleContentImgClick (e) {
      console.log(e)
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  .container
    background #fff
    margin-bottom .2rem
    .con-header
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
    .content
      position relative
      padding .2rem .2rem .35rem .2rem
      .content-title
        display flex
        font-size .24rem
        justify-content space-between
        margin-bottom .1rem
      .content-desc
        p
          color #616161
          font-size .26rem
          line-height .42rem
      .content-img
        position relative
        display flex
        flex-wrap wrap
        .img-wraper
          width 33.33333%
          box-sizing border-box
          padding .1rem
          img
            width 100%
        .img-tag
          position absolute
          display inline-block
          width .7rem
          border-radius .35rem 0 0 .35rem
          padding .1rem
          background: rgba(0,0,0,.6)
          font-size .24rem
          right 0.1rem
          bottom .3rem
          color #fff
    .content-footer
      height .88rem
      line-height .88rem
      text-align center
      color #616161
      z-index 2
  </style>
