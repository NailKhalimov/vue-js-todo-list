<template>
  <div id="app">
    <Header />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteToDo" />
  </div>
</template>

<script>
import Todos from "./components/Todos";
import Header from "./components/Layout/Header";

export default {
  name: "app",
  components: {
    Todos
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "todo One",
          completed: false
        },
        {
          id: 2,
          title: "todo Two",
          completed: false
        },
        {
          id: 3,
          title: "todo Three",
          completed: false
        }
      ]
    };
  },
  methods: {
    deleteToDo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    }
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>