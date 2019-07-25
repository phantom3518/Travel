<template>
    <div>
        <div class="title">热销</div>
        <ul v-for="item of recommendList" :key="item.id">
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
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: 'https://ss0.bdstatic.com/-0U0bnSm1A5BphGlnYG/tam-ogel/47d4d7de333622ac5a8f9ddd2c8ed3fd_78_59.jpg',
        title: '大连圣海洋世界',
        desc: '浪漫大连首站'
      }, {
        id: '0002',
        imgUrl: 'https://ss0.bdstatic.com/-0U0bnSm1A5BphGlnYG/tam-ogel/47d4d7de333622ac5a8f9ddd2c8ed3fd_78_59.jpg',
        title: '大连圣海洋世界',
        desc: '浪漫大连首站'
      }, {
        id: '0003',
        imgUrl: 'https://ss0.bdstatic.com/-0U0bnSm1A5BphGlnYG/tam-ogel/47d4d7de333622ac5a8f9ddd2c8ed3fd_78_59.jpg',
        title: '大连圣海洋世界',
        desc: '浪漫大连首站'
      }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
    @import "../../assets/styles/mixins.styl"
    .title
        margin-top: .2rem
        line-height .8rem
        background: #eee
        text-indent:.2rem
    .item-img-wrapper
        overflow hidden
        height: 0
        padding-bottom:33.9%
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
