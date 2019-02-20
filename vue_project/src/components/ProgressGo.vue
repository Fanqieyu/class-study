<template>
  <div class="load-bar" :style="allStyle">
    <div class="load-bar-inner" :style="oneStyle">
      <div class="num">{{percent}}%</div>
    </div>
  </div>
</template>

<script>
  export default {
    name: '',
    props: {
      percent: {
        type: [Number,String],
        default: 10
      },
      isVertical: {
        type: Boolean,
        deault: false
      },
      customImg: {
        type: String,
        default: ''
      }
    },
    data() {
      return {}
    },
    computed: {
      oneStyle() {
        return {
          width: `${this.percent}%`,
          backgroundImage: `url(${this.customImg})`
        }
      },
      allStyle() {
        return {
          transform: this.isVertical ? 'rotateZ(90deg)' : ''
        }
      }
    }
  }
</script>

<style lang="less" scoped>
  .load-bar {
    width: 70%;
    height: 20px;
    margin: 20px 5%;
    border-radius: 30px;
    background-color: #dcdbd7;
    box-shadow: 0 1px 0 rgba(255, 255, 255, 0.8), inset 0 2px 3px rgba(0, 0, 0, 0.2);
    transform-origin: 3% 10%;
    .load-bar-inner {
      height: 100%;
      margin-top: -6px;
      border-radius: inherit;
      background-color:rgb(223, 216, 128);
      background-size: auto 100%;
      background-position: center;
      background-repeat:repeat;
      .num {
        text-align: center;
      }
    }
  }
</style>

