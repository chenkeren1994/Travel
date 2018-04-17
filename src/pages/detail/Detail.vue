<template>
  <div>
    <detail-banner
      :sightName="sightName"
      :bannerImg="bannerImg"
      :bannerImgs="gallaryImgs"
    ></detail-banner>
    <detail-header></detail-header>
    <base-info :info="baseInfo"></base-info>
    <div class="content">
      <detail-list :list="list"></detail-list>
    </div>
    <user-commend :commends="commends"></user-commend>
    <detail-recommend :recommends="recommends"></detail-recommend>
    <my-footer></my-footer>
  </div>
</template>

<script>
import DetailBanner from './components/Banner.vue'
import DetailHeader from './components/Header.vue'
import DetailList from './components/List.vue'
import BaseInfo from './components/BaseInfo.vue'
import UserCommend from './components/UserCommend.vue'
import DetailRecommend from './components/Recommend.vue'
import MyFooter from 'common/footer/Footer'
import axios from 'axios'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList,
    BaseInfo,
    UserCommend,
    DetailRecommend,
    MyFooter
  },
  activated () {
    this.getDetailInfo()
  },
  mounted () {
    this.getDetailInfo()
  },
  data () {
    return {
      sightName: '',
      bannerImg: '',
      gallaryImgs: [],
      baseInfo: {},
      list: [],
      commends: [],
      recommends: []
    }
  },
  methods: {
    getDetailInfo () {
      axios.get('/api/detail.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(this.handleGetSuccess)
    },
    handleGetSuccess (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.gallaryImgs = data.gallaryImgs
        this.list = data.categoryList
        this.baseInfo = data.baseInfo
        this.commends = data.commends
        this.recommends = data.recommends
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
div
  background #f5f5f5
</style>
