<template>
  <div>
    <ul>
      <ToDoItem
          v-for="item_ToDoItem in todos_ToDoList"
          v-bind:key="item_ToDoItem"
          v-bind:item="item_ToDoItem"
          v-on:delete_item="to_delete_item"
      />  <!-- название массива, по которому делаем итерацию -->
    </ul>           <!-- название элемента="значение" -->
  </div>
</template>

<script>
import ToDoItem from "@/components/ToDoItem";

export default {
  props: [
    'todos_ToDoList'
  ],
  components: {
    ToDoItem
  },
  methods: {
    to_delete_item(id){
      //console.log(id)
      this.$emit("delete_item", id)
    }
  }
}
</script>

<style scoped>
  ul {
    list-style: none;
    margin: 0;
    padding: 0;
  }
</style>

<!--v-for="item in todos_ToDoList"
     v-bind:item_ToDoItem="item"-->