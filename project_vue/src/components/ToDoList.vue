<template>
  <div>
    <ul>
      <ToDoItem
          v-for="item_ToDoItem in todos_ToDoList"
          v-bind:key="item_ToDoItem"
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
  }
}
</script>

<style scoped>

</style>

<!--v-for="item in todos_ToDoList"
     v-bind:item_ToDoItem="item"-->