<template>
  <div class="click-counter">
    <div class="counter-num">次数: {{num}}</div>
    <button class="counter-btn" @click="handleClick">草拟吗!</button>
    <button class="counter-reset-btn" @click="handleResetClick">清零</button>
  </div>
</template>


<script>
export default {
  props: {
    initNum: {
      type: Number,
      default: 0
    }
  },

  data () {
    return {
      num: this.initNum
    }
  },

  methods: {
    handleClick () {
      this.num += 1
      this.notifyNum()
    },
    handleResetClick () {
      this.num = 0
    },
    notifyNum () {
      this.$emit('clicknum', {
        num: this.num
      })
    }
  }
}
</script>


<style>
.click-counter {
  display: flex;
  align-items: center;
  justify-content: center;
  border: 1px solid red;
  background-color: 10px;
}

.counter-num,
.counter-num,
.counter-reset-btn {
  flex: 1;
  margin: 3px;
}
</style>

