<template>
  <div id="app">
    <notice-bar :noticeBarList="noticeBarList"/>
  </div>
</template>

<script>
import NoticeBar from './components/NoticeBar.vue'

export default {
  name: 'App',
  components: {
    NoticeBar
  },
  data() {
    return {
      noticeBarList: [
        '第1条消息',
        '第2条消息',
        '第3条消息',
        '第4条消息',
        '第5条消息',
        '第6条消息',
        '第7条消息',
        '第8条消息',
        '第9条消息',
        '第10条消息',
        '第11条消息'
      ]
    }
  }
}
</script>

<style>
</style>
