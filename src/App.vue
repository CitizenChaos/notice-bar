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
        '11111',
        '22222'
      ]
    }
  }
}
</script>

<style>
</style>
