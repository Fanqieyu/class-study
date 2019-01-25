<template>
  <div id="app">
    <div class="off" v-for="(item, index) in light" :key="index" @click="lightshine(item)" :class="{'shine':item.done}"></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      light:[
        {index:1,status:0,done:false},
        {index:2,status:0,done:false},
        {index:3,status:0,done:false},
        {index:4,status:0,done:false},
        {index:5,status:0,done:false},
        {index:6,status:0,done:false},
        {index:7,status:0,done:false},
        {index:8,status:0,done:false},
        {index:9,status:0,done:false}
      ]
    }
  },
  methods: {
    lightshine(item) {
      this.light.forEach(e => {
        e.done = false;
      });
      if(item.status == 0) {
        item.status = 1;
        if(!item.done) {   //if是条件为true时才会执行的
          item.done = true;
        }
      }
    }
  }
}
</script>

<style>
  body {
    background: #20262E;
    /* padding: 20px; */
    font-family: Helvetica;
  }
  .off {
    width: 22px;
    height: 22px;
    border-radius: 50%;
    border: 2px solid blue;
    background-color: #fff;
    display: inline-block;
    margin-left: 10px;
  }
  .shine {
    background-color: yellow;
  }

</style>