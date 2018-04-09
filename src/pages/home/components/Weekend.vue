<template>
    <div>
      <div class="title">周末去哪儿</div>
      <ul>
        <li v-for="item in recommendList" :key="item.id" class="item border-bottom">
          <div class="item-img-wrapper">
            <img class="item-img" :src="item.imgUrl" :alt="item.title">
          </div>
          <div class="item-info">
            <p class="item-title">{{item.title}}</p>
            <p class="item-desc">{{item.desc}}</p>
          </div>
        </li>
      </ul>
    </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      recommendList: [
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/98/392c73a32d5ce0.jpg_r_640x214_bc565fa1.jpg',
          title: '沈阳必游TOP10',
          desc: '初入黑土地，玩味多彩人生'
        },
        {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1507/6b/70d17d828d87e1.jpg_r_640x214_6a995270.jpg',
          title: '周末游首选',
          desc: '当地人经常出没的地方'
        },
        {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/89/267342d404cbd7.jpg_r_640x214_8d8d1162.jpg',
          title: '亲子游乐',
          desc: '儿童的天堂，大人的回忆'
        },
        {
          id: '0004',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/10/6df2f495ab7425.jpg_r_640x214_96e2a04f.jpg',
          title: '兄弟·战无不胜',
          desc: '兄弟，一起战'
        },
        {
          id: '0005',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/bb/c8e77fc5811579.jpg_r_640x214_d740074b.jpg',
          title: '视觉沈阳',
          desc: '美轮美奂的海洋主题综合型亲子乐园'
        },
        {
          id: '0006',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/201301/17/488c835720fe935e93835fbb.jpg_200x200_dfe1c952.jpg',
          title: '沈阳森林动物园',
          desc: '奇异世界，五彩生活'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.title
    line-height .8rem
    background #eee
    margin-top .2rem
    text-indent .2rem
.item-img-wrapper
    overflow hidden
    height 0
    padding-bottom 33.9%
    .item-img
        width 100%
.item-info
    padding .1rem
    .item-title
        line-height .54rem
        font-size .28rem
        font-weight 1
    .item-desc
        font-size .24rem
        line-height .48rem
        color #616161
        ellipsis()
</style>
