<template>
  <div class="card" :class="card.status" @click="changecard">{{card.index}}</div>
</template>

<script>
  export default {
    name: '',
    components: {},
    props: {
      card: {
        type: Object
      }
    },
    methods: {
      changecard() {
        this.$emit('cardcolor',this.card)
      }
    }
  }
</script>

<style scoped>
  .card {
    width: 50px;
    height: 50px;
    background-color: antiquewhite;
    float: left;
    text-align: center;
    line-height: 50px;
    color: #246785;
    font-size: 30px;
    margin: 10px;
  }
  .last {
    background-color: #d188aa;
  }
  .now {
    background-color: #e7eb25;
  }
</style>
