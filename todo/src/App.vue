<template>
  <div id="app">
      <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>

import Todos from './components/Todos'

export default {
  name: 'App',
  components: {
    Todos
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Todo One",
          completed: false
        },
        {
          id: 2,
          title: "Todo two",
          completed: true
        },
        {
          id: 3,
          title: "Todo three",
          completed: false
        },
      ]
    }
  },
  methods: {
    deleteTodo(todoId) {
      this.todos = this.todos.filter(todo => todo.id != todoId)
    }
  }
}
</script>

<style>
 * {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
</style>
