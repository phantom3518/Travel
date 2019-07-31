<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点/游玩主题
    </div>
      <router-link to="/city">
        <div class="header-right">
          {{this.$store.state.city}}
          <span class="iconfont arrow-icon">&#xe600;</span>
        </div>
      </router-link>
  </div>
</template>

<script>

export default {
  name: 'HomeHeader',
  components: {
  }
}
</script>
<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles.styl'
  .header
    display flex
    height: $headerHeight
    line-height: $headerHeight
    background: $bgColor
    color: #fff
    .header-left
      width .64rem
      float: left
      .back-icon
        text-align: center
        font-size: .4rem
    .header-input
      flex :1
      background: #fff
      margin-top: .12rem
      height: .64rem
      padding-left: .2rem
      color #ccc
      line-height: .64rem
      border-radius .1rem
    .header-right
      color white
      min-width: 1.04rem
      padding: 0 .1rem
      float: right
      text-align: center
      .arrow-icon
          margin-left: -.03rem
          font-size: .24rem
</style>
