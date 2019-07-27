<template>
    <div class="header">
        城市选择
        <router-link to="/">
            <div class="iconfont header-back">&#xe624;</div>
        </router-link>
    </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
    @import '~@/assets/styles/varibles.styl';
    .header
        overflow: hidden;
        position: relative
        height: $headerHeight
        line-height: $headerHeight
        color: #fff;
        text-align: center
        background: $bgColor
        font-size: .32rem
        .header-back
            position: absolute
            top: 0
            left: 0
            width: .64rem
            text-align: center
            font-size: .4rem
            color #fff
</style>
