<template>
  <div>
    <div class="banner" @click="handleBannerClick">
        <img class="banner-img" src="//img1.qunarzz.com/sight/p0/201401/22/29477dff4c882ff4a1bb81e20c371c5e.jpg_600x330_e993d621.jpg" alt="">
        <div class="banner-info">
          <div class="banner-title">张氏帅府(AAAA景区)</div>
          <div class="banner-number">
            <span class="iconfont banner-icon">&#xe692;</span>39
          </div>
        </div>
    </div>
    <common-galary @close="handleGallaryClose" v-show="showGallary" :imgs="imgs"></common-galary>
  </div>
</template>

<script>
import CommonGalary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  data () {
    return {
      imgs: ['http://img1.qunarzz.com/sight/p0/1607/bf/bf66af67fa768b3cc0.water.jpg_r_800x800_74daad4e.jpg'],
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
    CommonGalary
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position relative
    overflow hidden
    height 0
    padding-bottom 55%
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
