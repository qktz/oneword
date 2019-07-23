<template>
  <div class="container">
    <div class="message">{{msg}}</div>
    <click-counter :init-num="10" @clicknum="handleClickNum" />
    <i-button type="primary" @click="bindViewTap">按钮一个</i-button>
  </div>
</template>


<script>
import ClickCounter from '@/components/click-counter'

export default {
  components: { ClickCounter },

  data () {
    return {
      msg: 'click me'
    }
  },

  methods: {
    clickHandle () {
      this.msg = 'you clicked!!!'
    },
    handleClickNum (data) {
      console.log('>>>>>>', data.num)
    },
    bindViewTap () {
      console.log('typed')
    }
  }
}
</script>


<style>
page{
  height:100%;
}
.container {
  background: blueviolet;
  height: 100%;
  color: red;
  text-align: center;
}
</style>
