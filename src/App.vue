<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/todo.png">
    <HelloWorld msg="Welcome to Your To-Do App"/>
    <toDoInput></toDoInput>

  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import toDoInput from './components/toDoInput.vue'


export default {
  name: 'App',
  components: {
    HelloWorld,
    toDoInput
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
