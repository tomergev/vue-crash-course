<template>
  <div id="app">
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Todos from "./components/Todos";

export default {
  name: "app",
  components: {
    Todos
  },
  data: () => ({
    todos: [
      {
        id: 1,
        title: "Todo One",
        completed: false
      },
      {
        id: 2,
        title: "Todo Two",
        completed: false
      },
      {
        id: 3,
        title: "Todo Three",
        completed: false
      }
    ]
  }),
  methods: {
    deleteTodo(idToDel) {
      this.todos = this.todos.filter(({ id }) => id !== idToDel);
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
