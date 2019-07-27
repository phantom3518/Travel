<template>
    <div>
        <div class="title">热销</div>
        <ul v-for="item of weekendList" :key="item.id">
            <li class="item">
                <div class="item-img-wrapper">
                    <img class="item-img" :src="item.imgUrl">
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
    weekendList: Array
  },
  data () {
    return {

    }
  }
}
</script>

<style lang="stylus" scoped>
    @import "../../assets/styles/mixins.styl"
    .title
        line-height .8rem
        background: #eee
        text-indent:.2rem
    .item-img-wrapper
        overflow hidden
        height: 0
        padding-bottom:37%
        .item-img
            width: 100%
    .item-title
        line-height: .54rem
        font-size: .3rem
        text-indent .1rem
        ellipse()
    .item-desc
        line-height:.4rem
        text-indent .1rem
        color #ccc
        ellipse()
</style>
