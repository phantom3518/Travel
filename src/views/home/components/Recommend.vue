<template>
    <div>
        <div class="title">热销</div>
        <ul>
                <router-link
                    tag="li"
                    class="item"
                    v-for="item of recommendList"
                    :key="item.id"
                    :to="'/detail/' + item.id"
                >
                    <img class="item-img" :src="item.imgUrl">
                    <div class="item-info">
                        <p class="item-title">{{item.title}}</p>
                        <p class="item-desc">{{item.desc}}</p>
                        <button class="item-button">查看详情</button>
                    </div>
                </router-link>
        </ul>
    </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    recommendList: Array
  },
  data () {
    return {

    }
  }
}
</script>

<style lang="stylus" scoped>
    @import "../../../assets/styles/mixins.styl"
    .title
        margin-top: .2rem
        line-height .8rem
        background: #eee
        text-indent:.2rem
    .item
        overflow hidden
        display flex
        height: 1.9rem
        .item-img
            width: 1.7rem
            height: 1.7rem
            padding: .1rem
        .item-info
            flex 1
            min-width 0
            padding: .1rem
            .item-title
                line-height: .54rem
                font-size: .32rem
                /*overflow hidden*/
                /*white-space: nowrap*/
                ellipse()
            .item-desc
                line-height:.4rem
                color #ccc
                ellipse()
            .item-button
                line-height: .44rem
                margin-top: .16rem
                background: #ff9300
                padding: 0 .2rem
                border-radius .06rem
                color white
</style>
