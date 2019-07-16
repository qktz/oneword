<template>
  <div class="container" @click="clickHandle">
    <div class="message">{{msg}}</div>
    <click-counter :init-num="10" @clicknum="handleClickNum" />
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
    }
  }
}
</script>


<style scoped>
.message {
  color: red;
  padding: 10px;
  text-align: center;
}
</style>
