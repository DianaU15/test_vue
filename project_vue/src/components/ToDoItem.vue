<template>
  <div>
    <li>
      <span v-bind:class="{done: todo.completed}" >
        <input type="checkbox"
               v-on:change="markCompleted" >
        <strong>{{todo.title}}</strong>
      </span>
      <button class="b-del"
              v-on:click="$emit('delete_item', todo.id)">&times;</button>
    </li>
  </div>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
      required: true
    }
  },
  data() {
    return {
      todo: this.item
    }
  },
  methods: {
    markCompleted() {
      this.todo.completed = !this.todo.completed
    },
  }
}
</script>

<style scoped>
  li {
    border: 2px solid #ccc;
    display: flex;
    justify-content: space-between;
    padding: .5rem 2rem;
    margin-bottom: 1rem;
  }
  .b-del {
    background: red;
    color: #fff;
    border-radius: 40%;
    font-weight: bold;
  }

  .done {
    text-decoration: line-through;
  }



</style>