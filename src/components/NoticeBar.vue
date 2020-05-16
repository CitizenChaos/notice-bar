<template>
  <div
    class="list_wrapper"
    :style="[wrapperHeightStyle, wrapperBgcStyle, wrapperColorStyle]"
  >
    <transition name="slide">
      <p class="text" :key="text.id">{{ text.val }}</p>
    </transition>
  </div>
</template>

<script>
/**
 * 纵向滚动组件
 *
 * 参数说明
 * @param {*} noticeBarList 消息数组
 * @param {*} speed 速度（毫秒）
 * @param {*} height 高度（px）
 * @param {*} background 背景色
 * @param {*} color 字体颜色
 *
 */
export default {
  name: 'scroll',
  props: {
    noticeBarList: {
      type: Array,
      default: () => {
        return []
      }
    },
    speed: {
      type: Number,
      default: 2000
    },
    height: {
      type: Number,
      default: 40
    },
    background: {
      type: String,
      default: '#fff'
    },
    color: {
      type: String,
      default: '#000'
    }
  },
  data() {
    return {
      number: 0,
      timer: {}
    }
  },
  computed: {
    text() {
      return {
        id: this.number,
        val: this.noticeBarList[this.number]
      }
    },
    wrapperHeightStyle() {
      return {
        height: this.height + 'px',
        lineHeight: this.height + 'px'
      }
    },
    wrapperBgcStyle() {
      return {
        background: this.background
      }
    },
    wrapperColorStyle() {
      return {
        color: this.color
      }
    }
  },
  mounted() {
    this.startMove()
  },
  methods: {
    startMove() {
      this.timer = setTimeout(() => {
        if (this.number === this.noticeBarList.length - 1) {
          this.number = 0
        } else {
          this.number += 1
        }
        this.startMove()
      }, this.speed)
    }
  }
}
</script>

<style scoped>
.list_wrapper {
  overflow: hidden;
  position: relative;
  text-align: center;
}
.text {
  width: 100%;
  position: absolute;
  bottom: 0;
  padding: 0;
  margin: 0;
}
.slide-enter-active,
.slide-leave-active {
  transition: all 0.5s linear;
}
.slide-enter {
  transform: translateY(40px) scale(1);
  opacity: 1;
}
.slide-leave-to {
  transform: translateY(-40px) scale(0.8);
  opacity: 0;
}
</style>
