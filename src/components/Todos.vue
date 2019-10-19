<template>
  <div>
    <div v-for="todo in todos" v-bind:key="todo.id">
      <ToDoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" />
    </div>
  </div>
</template>

<script>
import ToDoItem from "./TodoItem";

export default {
  name: "Todos",
  components: {
    ToDoItem
  },
  props: ["todos"]
};
</script>

<style scoped>
</style>