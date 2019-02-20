<template>
  <div class="progress-set">
    <h3>设置</h3>
    <div class="setting">
      <input type="range" max="100" min="0" step="10" v-model="percent">
      <div class="set-position" @click="changePosition">{{isVertical ? '水平' : '垂直'}}</div>
    </div>
  </div>
</template>

<script>
  export default {
    name: '',
    data() {
      return {
        percent: 10
      }
    },
    components: {},
    props: {
      isVertical: {
        type: Boolean
      }
    },
    methods: {
      changePosition() {
        this.$emit('handlePosition')
      }
    },
    watch: {
      percent(v) {  //监听v-model双向绑定
        this.$emit('handleChange', v)
      }
    }
  }
</script>

<style lang="less" scoped>
  .progress-set {
    background-color: #f1ece5;
    margin: 0 5% 20px 10%;
    border-radius: 20px;
    h3 {
      text-align: center;
    }
    .setting {
      display: flex;
      justify-content: space-around;
      aligh-items: center;
      min-height: 100px;
      .set-position {
        text-align: center;
        background-color: rgb(223, 216, 128);
        color: white;
        font-weight: 600;
        padding: 10px;
        height: 10%;
        margin-top: 25px;
      }
    }
  }
</style>


