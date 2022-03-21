<template>
  <div id="app">
    <h1>ToDoApp</h1>
    <hr>    <!-- горизонтальная черта -->
    <ToDoList v-bind:todos_ToDoList="todos_App"></ToDoList>
  </div>
</template>

<script>
import ToDoList from "@/components/ToDoList";

export default {
  name: 'App',
  data() {
    return{
      todos_App: [
        {id: 1, title:'Задание 1', completed: false},
        {id: 2, title:'Задание 2', completed: false},
        {id: 3, title:'Задание 3', completed: false},
      ]
    }
  },
  components: {
    ToDoList
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
