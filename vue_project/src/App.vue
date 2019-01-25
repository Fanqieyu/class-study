<template>
  <div id="app">
    <!-- <todo-list></todo-list> -->
    <!-- <light-shine></light-shine> -->
    <star-box></star-box>
    <!-- <card-father></card-father> -->
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TodoList from './components/TodoList.vue'
import LightShine from './components/LightShine.vue'
import StarBox from './components/StarBox.vue'
import CardFather from './components/CardFather.vue'
export default {
  name: 'app',
  components: {
      HelloWorld,
      TodoList,
      LightShine,
      StarBox,
      CardFather
  }
}
</script>

<style>
  body {
    background: rgb(100, 134, 179);
    /* padding: 20px; */
    font-family: Helvetica;
  }

  #app {
    /* background: #fff; */
    border-radius: 4px;
    padding: 20px 0;
    transition: all 0.2s;
  }
</style>
