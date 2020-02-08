<template>
    <div>
        <city-header></city-header>
        <city-search :cities="cities"></city-search>
        <city-list :hotCities="hotCities" :cities="cities" :letter="letter"></city-list>

        <!--<div class="list" ref="wrapper">-->
            <!--<div>-->
                <!--<div class="area">-->
                    <!--<div class="title border-topbottom">当前城市</div>-->
                    <!--<div class="button-list">-->
                        <!--<div class="button-wrap">-->
                            <!--<div class="button">{{this.$store.state.city}}</div>-->
                        <!--</div>-->
                    <!--</div>-->
                <!--</div>-->
                <!--<div class="area">-->
                    <!--<div class="title border-topbottom">热门城市</div>-->
                    <!--<div class="button-list">-->
                        <!--<div-->
                            <!--class="button-wrap"-->
                            <!--v-for="item of hotCities"-->
                            <!--:key="item.id"-->
                            <!--@click="handleCityClick(item.name)"-->
                        <!--&gt;-->
                            <!--<div class="button">{{item.name}}</div>-->
                        <!--</div>-->
                    <!--</div>-->
                <!--</div>-->
                <!--<div class="area" v-for="(list,key) of cities" :key="key" :ref="key">-->
                    <!--<div class="title border-topbottom">{{key}}</div>-->
                    <!--<div class="item-list">-->
                        <!--<div-->
                            <!--class="item border-bottom"-->
                            <!--v-for="item of list"-->
                            <!--:key="item.id"-->
                            <!--@click="handleCityClick(item.name)"-->
                        <!--&gt;{{item.name}}</div>-->
                    <!--</div>-->
                <!--</div>-->

            <!--</div>-->
        <!--</div>-->
        <!---->
        <city-alphabet @change="handleLetterChange" :cities="cities"></city-alphabet>
    </div>
</template>

<script>
import axios from 'axios'
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
import Bscroll from 'better-scroll'
export default {
  name: 'city',
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  data () {
    return {
      cities: {},
      hotCities: [],
      letter: ''
    }
  },
  methods: {
    getCityInfo () {
      axios.get('static/mock/city.json')
        .then(this.handleGetCityInfoSucc)
    },
    handleGetCityInfoSucc (res) {
      res = res.data
      this.cities = res.data.cities
      this.hotCities = res.data.hotCities
      console.log(res.data)

      // console.log(res.data)
      // console.log(res.data.cities)
    },
    handleLetterChange (letter) {
      // console.log(letter)
      this.letter = letter
    },
    handleCityClick (city) {
      this.$store.commit('changeCity', city)
      this.$router.push('/')
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
  created () {
    this.getCityInfo()
  },
  mounted () {
    this.$nextTick(() => {
      this.scroll = new Bscroll(this.$refs.wrapper, {
      })
    })
  }
}
</script>

<style lang="stylus" scoped>

</style>
