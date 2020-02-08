<template>
    <scroll ref="wrapper"
            :listenScroll="true"
            :pullup="true"
            :data="arrList"
            @scrollToEnd="scrollToEnd"
            @setScroll="setScroll"
            @beforeScroll = "beforeScroll"
           >

        <ul>
            <li v-for="(item,i) in arrList" :key="i">{{item}}{{i}}</li>

        </ul>

    </scroll>
</template>
<script>
import Scroll from '@/components/Scroll.vue'
export default {
  components: {
    Scroll
  },
  data () {
    return {
      arrList: [
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据',
        '测试数据'
      ],
      scroll: null
    }
  },
  methods: {
    scrollToEnd (scroll) {
      this.scroll = scroll
      console.log('下拉到最底下')
    },
    setScroll (scroll) {
      this.scroll = scroll
      console.log('scroll创建成功')
    },
    // scroll (pos) {
    //   console.log(pos)// 监听滚动坐标
    // },
    beforeScroll () {
      console.log('滚动之前')
    }
  }
}
</script>
