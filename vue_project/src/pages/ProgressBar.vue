<template>
  <div class="progress-bar">
    <h1>进度条</h1>
    <progress-go :percent="percent" :isVertical="isVertical" :customImg="customImg"></progress-go>
    <progress-set @handlePosition="changePosition" @handleChange="changePercent" :isVertical="isVertical"></progress-set>
    <div class="imagebox">
      <h3>自定义皮肤</h3>
      <div v-for="item in imgs" :key="item">
        <img :src="item" @click="changeImg(item)"/>
      </div>
    </div>
  </div>
</template>

<script>
  /* eslint-disable */
  import ProgressGo from '../components/ProgressGo.vue'
  import ProgressSet from '../components/ProgressSet.vue'
  export default {
    name: '',
    components: {
      ProgressGo,
      ProgressSet
    },
    data() {
      return {
        percent: 10,
        isVertical: false,
        customImg: '',
        imgs: [
          require('../img/progressImg/bgg1.png'),
          require('../img/progressImg/bgg2.png'),
          require('../img/progressImg/bgg3.png'),
          require('../img/progressImg/bgg4.png'),
          require('../img/progressImg/bgg5.png'),
          require('../img/progressImg/bgg6.png')
        ]
      }
    },
    methods: {
      changePosition() {
        this.isVertical = !this.isVertical
      },
      changeImg(item) {
        this.customImg = item;
      },
      changePercent(v) {
        this.percent = v;
        if(this.percent == 50 || this.percent == 100) {
          console.log('埋点-到达50或100');
        }
      }
    }
  }
</script>

<style lang="less" scoped>
  .progress-bar {
    h1 {
      text-align: center;
      color: rgb(100, 134, 179);
    }
    padding: 50px 0;
    width: 100%;
    height: 85%;
    background-color: #f5f5f5;
    box-sizing: border-box;
    position: fixed;
    overflow: scroll;
    .imagebox {
      background-color: #f1ece5;
      margin: 0 5% 20px 10%;
      border-radius: 20px;
      padding: 2% 5%;
      h3 {
        text-align: center;
        margin-bottom: 10px;
      }
      div {
        width: 22%;
        height: 30px;
        border-radius: 10px;
        float: left;
        margin: 2% 6%;
        overflow: hidden;
        text-align: center;
        box-shadow: 0 0 6px #d188aa;
        img {
          width: auto;
          height: 100%;
        }
      }
    }
    .imagebox::after{
      content: '';
      display: block;
      clear: both;
    }
  }
</style>


