<template>
  <div class="customorder">
    <button @click="handleClick">addNum</button>
    <h1 v-if="count<6" v-change="count">it is a custom directive</h1>
    <!-- <button @click="handleColor">changeColor</button>
    <h2 v-change-background-color="myBgColor">it is a color change</h2> -->
  </div>
</template>

<script>
  export default {
    data() {
      return {
        count: 0,
        myBgColor: '#696969'
      }
    },
    methods: {
      handleClick: function() {
        //按钮单击，count自增
        this.count++;
        console.log(this.count);

      },
      handleColor: function() {
        this.myBgColor = 'yellow';
      }
    },
    directives: {
      change: {
        bind: function(el,bindings) {
          console.log('指令已经绑定到元素了');
          console.log(el);
          console.log(bindings);
          //准备 将传递进来的参数显示在调用该指令的元素的innerHTML
          el.innerHTML = bindings.value;
        },
        //update 值更新时的工作
        update: function(el,bindings) {
          console.log('指令的数据有所变化')
          el.innerHTML = bindings.value;
          if(bindings.value == 5) {
            console.log('it is a test')
          }
          setTimeout(() => {
            alert('2s前数字变化了');
          }, 2000);
        },
        unbind: function() {
          console.log('解除绑定了');
        }
      },
      changeBackgroundColor: {
        bind: function(el, bindings) {
          console.log('绑定颜色了');
          console.log(bindings.value);
          el.style.backgroundColor = bindings.value;
        },
        update: function(el, bindings) {
          console.log('颜色变化了');
          el.style.backgroundColor = bindings.value;
        }
      }
    }

  }
</script>

<style lang="less" scoped>
  .customorder {
    h1 {
      text-align: center;
    }
    button {
      border-radius: 10px;
      background-color: pink;
      border: none;
      padding: 5px 10px;
      text-align: center;
      margin: 10px;
      box-shadow: 0 0 10px 2px rgb(206, 206, 46);
    }
  }
</style>


