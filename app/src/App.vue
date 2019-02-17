<template>
  <div id="app">
    <Header />
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import  Header from './components/layout/Header';
import Todos from './components/Todos';
import AddTodo from './components/AddTodo';


export default {
  name: "app",
  components: {
    Header,
    Todos,
    AddTodo
  },
  data(){
    return {
      todos: [
        {
          id: 1,
          title: "Todo Item One",
          completed: false
        },
        {
          id: 2,
          title: "Todo Item Two",
          completed: true
        },
        {
          id: 3,
          title: "Todo Item Three",
          completed: false
        },
      ],
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id != id);
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
    }
  },
}

</script>

<style lang="scss">

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
 font-family: 'Courier New', Courier, monospace;
}
</style>
