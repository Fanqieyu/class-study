<template>
  <div id="app">
    <div>点亮我们~但是每个只能一次噢~</div>
    <star v-for="(item, index) in light" :key="index" :starbling="item" @lightnow="lightnow"></star>
  </div>
</template>

<script>
  import star from './star'
  export default {
    name: '',
    components: {
      star
    },
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
      lightnow(index) {   //子组件传来的index
        this.light.forEach((item) => {
          item.done = false
          if(item.status == 0){
            if(index == item.index) {  //当子组件的index等于父组件循环到的某一个index
              item.status = 1
              item.done = true
            }        
          }
        })
      }
    }
  }
</script>

<style>

</style>


