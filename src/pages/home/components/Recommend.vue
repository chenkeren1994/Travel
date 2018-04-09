<template>
    <div>
      <div class="title">热销推荐</div>
      <ul>
        <li v-for="item in recommendList" :key="item.id" class="item border-bottom">
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
  data () {
    return {
      recommendList: [
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1509/99/990b3e72493bf6f2.img.jpg_150x150_5a19cb12.jpg',
          title: '沈阳故宫',
          desc: '近期小伙伴们收藏最！多！的景点😊'
        },
        {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1706/23/238f540754b2bdd1a3.water.jpg_200x200_86c3c010.jpg',
          title: '七星海世界',
          desc: '美轮美奂的海洋主题综合型亲子乐园'
        },
        {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/201301/17/488c835720fe935e93835fbb.jpg_200x200_dfe1c952.jpg',
          title: '沈阳森林动物园',
          desc: '9月27日，到熊猫馆看“滚滚”来！'
        },
        {
          id: '0004',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1509/99/990b3e72493bf6f2.img.jpg_150x150_5a19cb12.jpg',
          title: '沈阳故宫',
          desc: '近期小伙伴们收藏最！多！的景点😊'
        },
        {
          id: '0005',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1706/23/238f540754b2bdd1a3.water.jpg_200x200_86c3c010.jpg',
          title: '七星海世界',
          desc: '美轮美奂的海洋主题综合型亲子乐园'
        },
        {
          id: '0006',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/201301/17/488c835720fe935e93835fbb.jpg_200x200_dfe1c952.jpg',
          title: '沈阳森林动物园',
          desc: '9月27日，到熊猫馆看“滚滚”来！'
        }
      ]
    }
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
      margin-top .16rem
      color #fff
      background #ff9300
      padding 0 .2rem
      border-radius .06rem
      ellipsis()
</style>
