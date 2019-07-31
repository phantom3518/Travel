<template>
    <div class="list" ref="wrapper">
        <div>
            <div class="area">
                <div class="title border-topbottom">当前城市</div>
                <div class="button-list">
                    <div class="button-wrap">
                        <div class="button">{{this.$store.state.city}}</div>
                    </div>
                </div>
            </div>
            <div class="area">
                <div class="title border-topbottom">热门城市</div>
                <div class="button-list">
                    <div
                        class="button-wrap"
                        v-for="item of hotCities"
                        :key="item.id"
                        @click="handleCityClick(item.name)"
                    >
                        <div class="button">{{item.name}}</div>
                    </div>
                </div>
            </div>
            <div class="area" v-for="(list,key) of cities" :key="key" :ref="key">
                <div class="title border-topbottom">{{key}}</div>
                <div class="item-list">
                    <div
                        class="item border-bottom"
                        v-for="item of list"
                        :key="item.id"
                        @click="handleCityClick(item.name)"
                    >{{item.name}}</div>
                </div>
            </div>

        </div>
    </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CityList',
  props: {
    cities: Object,
    hotCities: Array,
    letter: String
  },
  methods: {
    handleCityClick (city) {
      this.$store.commit('changeCity', city)
      this.$router.push('/')
      // this.$store.dispatch('changeCity', city)
      // alert(city)
    }
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        // console.log(element)
        this.scroll.scrollToElement(element)
      }
      // console.log(this.letter)
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  }
}
</script>

<style lang="stylus" scoped>
    @import '~@/assets/styles/varibles.styl';
    .border-topbottom
        &:before
            border-color: #ccc
        &:after
            border-color: #ccc
    .border-bottom
        &:before
            border-color: #ccc
    .list
        overflow: hidden
        position: absolute
        top: 1.68rem
        left: 0
        right: 0
        bottom: 0
        .title
            line-height: .54rem
            background: #eee
            padding-left: .2rem
            color #666
            font-size: .26rem
        .button-list
            padding: .1rem .6rem .1rem .1rem
            overflow hidden
            .button-wrap
                float: left
                width: 33.33%
                .button
                    margin: .1 rem
                    padding: .1rem
                    text-align: center
                    border-radius: .06rem
                    border: .02rem solid #ccc
    .item-list
        .item
            line-height: .76rem
            padding-left: .2rem
</style>
