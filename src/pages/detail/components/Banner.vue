<template>
  <div>
    <div class="banner" @click="handleBannerClick">
        <img class="banner-img" :src="bannerImg" alt="">
        <div class="banner-info">
          <div class="banner-title">{{sightName}}</div>
          <div class="banner-number">
            <span class="iconfont banner-icon">&#xe692;</span>{{bannerImgs.length}}
          </div>
        </div>
    </div>
    <fade-animation>
      <common-galary @close="handleGallaryClose" v-show="showGallary" :imgs="bannerImgs"></common-galary>
    </fade-animation>
  </div>
</template>

<script>
import CommonGalary from 'common/gallary/Gallary'
import FadeAnimation from 'common/fade/FadeAnimation'
export default {
  name: 'DetailBanner',
  props: {
    sightName: {
      type: String
    },
    bannerImg: {
      type: String
    },
    bannerImgs: {
      type: Array
    }
  },
  data () {
    return {
      showGallary: false
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  },
  components: {
    CommonGalary,
    FadeAnimation
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position relative
    overflow hidden
    height 0
    padding-bottom 55%
    z-index 2
    .banner-img
      width 100%
    .banner-info
      position absolute
      display flex
      left 0
      right 0
      bottom 0
      height .6rem
      color #fff
      background-image linear-gradient(top, rgba(0,0,0,0),rgba(0,0,0,.8))
      .banner-title
        flex 1
        font-size .32rem
        padding 0 .2rem
        margin-top .14rem
      .banner-number
        margin-top .14rem
        padding 0 .4rem
        line-height .32rem
        height .32rem
        font-size .24rem
        border-radius .2rem
        background rgba(0,0,0,.8)
        .banner-icon
          font-size .24rem
</style>
