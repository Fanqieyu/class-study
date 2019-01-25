<template>
  <div id="app">
      <div>
        <button @click="asc">创建时间排序 - 正序</button>
        <button @click="desc">创建时间排序 - 倒序</button>
      </div>
      <div>
        <input v-model="text"><button @click="addItem">add</button>
      </div>
      <h3>未完成的</h3>
      <ul>
        <li v-for = 'todo in todoList' @click="end(todo)">{{todo.text}}</li>
      </ul>
      <h3>已完成的</h3>
      <ul>
        <li v-for = 'todo in finishList'>{{todo.text}}</li>
      </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todos: [
        {
          text: '吃饭',
          isdone: false,
          createTime: new Date('2018-12-29').getTime()
        },
        {
          text: '睡觉',
          isdone: false,
          createTime: new Date('2018-12-30').getTime()
        },
        {
          text: '学习',
          isdone: false,
          createTime: Date.now()
        }
      ],
      text: ''
    }
  },
  methods: {
    addItem() {
      this.todos.push({
        text: this.text,
        isdone: 0,
        createTime: new Date().getTime()
      });
      this.text= ''
    },
    end(todo) {
      todo.isdone = true;
    },
    asc() {
      return this.todos.sort((a,b) => {
        return a.createTime - b.createTime;
      })
    },
    desc() {
      return this.todos.sort((a,b) => {
        return b.createTime - a.createTime;
      })
    }
  },
  computed: {
    // filter 根据返回值是true还是false决定保留还是丢弃该元素。
    todoList: function() {   //未完成
      return this.todos.filter((todo) => {
        return !todo.isdone;
      })
    },
    finishList: function() {  //已完成
      return this.todos.filter((todo) => {
        return todo.isdone;
      })
    }
  }
}
</script>

<style scoped>
  body {
    background: #20262E;
    padding: 20px;
    font-family: Helvetica;
  }

  #app {
    background: #fff;
    border-radius: 4px;
    padding: 20px;
    transition: all 0.2s;
  }
  button {
    margin: 6px;
    background-color: gray;
    border-radius: 10px;
    color: white;
  }
  .done {
    color: #666;
    text-decoration: line-through;
  }
</style>
