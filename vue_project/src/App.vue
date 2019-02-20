<template>
  <div id="app">
    <!-- <todo-list></todo-list> -->
    <!-- <light-shine></light-shine> -->
    <!-- <star-box></star-box> -->
    <!-- <card-father></card-father> -->
    <progress-bar></progress-bar>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TodoList from './components/TodoList.vue'
import LightShine from './components/LightShine.vue'
import StarBox from './components/StarBox.vue'
import CardFather from './components/CardFather.vue'
import ProgressBar from './pages/ProgressBar.vue'
export default {
  name: 'app',
  components: {
      HelloWorld,
      TodoList,
      LightShine,
      StarBox,
      CardFather,
      ProgressBar
  }
}
</script>

<style>
  body {
    background: rgb(100, 134, 179);
    /* padding: 20px; */
    font-family: Helvetica;
    margin: 0;
  }

  #app {
    /* background: #fff; */
    border-radius: 4px;
    padding: 20px 0;
    transition: all 0.2s;
  }

      section,div,ul,li,h1,h2,h3{
        margin: 0;
        padding: 0;
    }
</style>
