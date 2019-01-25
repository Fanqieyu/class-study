<template>
  <div class="allword" v-show="last||now">
    你刚刚点的是{{last}}号卡片，我是{{now}}号卡片,我们加起来是{{total}}
  </div>
</template>

<script>
  export default {
    name:'',
    props: {
      last: {
        type: Number,
        default: 0
      },
      now: {
        type: Number,
        default: 0
      }
    },
    computed: {
      total() {
        return this.last + this.now
      }
    }
  }
</script>

<style scoped>
  .allword {
    width: 100%;
    font-size: 20px;
    color:brown;
    margin-top: 20px;
  }
  .word {
    display: inline-block;
  }
</style>
