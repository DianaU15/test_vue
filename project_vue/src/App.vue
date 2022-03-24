<template>
  <div id="app">
    <h1>ToDoApp</h1>
    <AddItem
        v-on:add_todo="to_add_item">
    </AddItem>
    <hr>    <!-- горизонтальная черта -->
    <ToDoList
        v-bind:todos_ToDoList="todos_App"
        v-on:delete_item="to_delete_item"
    ></ToDoList>
 </div>
</template>

<script>
import ToDoList from "@/components/ToDoList";
import AddItem from "@/components/AddItem";

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
   ToDoList,
   AddItem
 },
  methods: {
   to_delete_item(id){
     this.todos_App = this.todos_App.filter(t=>t.id !== id)
   },
    to_add_item(item){
      this.todos_App.push(item)
    }
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
