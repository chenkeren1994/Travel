<template>
    <div>
      <div class="title">周末去哪儿</div>
      <ul>
        <li v-for="item in list" :key="item.id" class="item border-bottom">
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
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.title
    line-height .8rem
    background #eee
    text-indent .2rem
.item-img-wrapper
    overflow hidden
    height 0
    padding-bottom 37.09%
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
