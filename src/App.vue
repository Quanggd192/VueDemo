<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <Todos v-bind:todos="todos" v-on:del-todo="delTodo"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Todos from "./components/todos.vue"
export default {
  name: 'app',
  components: {
    HelloWorld, Todos
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "todo 1",
          complete: false
        },
        {
          id: 2,
          title: "todo 2",
          complete: false
        },
        {
          id: 3,
          title: "todo 3",
          complete: false
        }
      ]
    }
  },
  methods:{
    delTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
