<template>
  <div id="app">
    <!-- <todo-list></todo-list> -->
    <!-- <light-shine></light-shine> -->
    <!-- <star-box></star-box> -->
    <!-- <card-father></card-father> -->
    <!-- <progress-bar></progress-bar> -->
    <!-- <custom-order></custom-order> -->
    <!-- <table-list-me></table-list-me> -->
    <!-- <table-list></table-list> -->
    <table-row></table-row>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TodoList from './components/TodoList.vue'
import LightShine from './components/LightShine.vue'
import StarBox from './components/StarBox.vue'
import CardFather from './components/CardFather.vue'
import ProgressBar from './pages/ProgressBar.vue'
import CustomOrder from './pages/CustomOrder.vue'
import TableListMe from './pages/TableListMe.vue'
import TableList from './pages/TableList.vue'
import TableRow from './pages/TableRow.vue'
export default {
  name: 'app',
  components: {
      HelloWorld,
      TodoList,
      LightShine,
      StarBox,
      CardFather,
      ProgressBar,
      CustomOrder,
      TableListMe,
      TableList,
      TableRow
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
