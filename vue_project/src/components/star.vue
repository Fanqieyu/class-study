<template>
  <div class="starbox">
    <div class="star-item" @click="light" :class="{'colorchange':starbling.done}"></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
    }
  },
  methods: {
    light() {
      this.$emit("lightnow",this.starbling.index) //用来确定是哪个子组件往上传值
    }
  },
  props: {
    starbling: {
      type: Object
    }
  }
}
</script>

<style scoped>
  .star-item {
    width: 22px;
    height: 22px;
    border-radius: 50%;
    border: 2px solid #696;
    background-color: aliceblue;
    display: inline-block;
    margin-left: 10px;
  }
  .colorchange {
    background-color: yellow;
  }
</style>
