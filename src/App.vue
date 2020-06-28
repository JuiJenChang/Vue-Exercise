<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <TodoList />
    <FetchApi />
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue'
import FetchApi from './components/FetchApi.vue'

export default {
  name: 'App',
  components: {
    TodoList,
    FetchApi
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
