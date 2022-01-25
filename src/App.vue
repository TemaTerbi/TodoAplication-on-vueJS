<template>
  <div id="app">
    <h1>Todo Aplication</h1>
    <addTask @add-task="addTask"/>
  </div>
  <TodoList v-bind:todos="todos" @remove-task="removeTask" v-if="todos.length"/>
  <p v-else>No Todos!</p>
</template>

<script>
import TodoList from '@/components/TodoList'
import addTask from '@/components/addTask'

export default {
  name: 'App',
  data() {
    return {
      todos: [
        {id: 1, title:'Купить молоко', completed: false},
        {id: 2, title:'Купить хлеб', completed: false},
        {id: 3, title:'Купить масло', completed: false}
      ]
    }
  },
  components: {
    TodoList,
    addTask
  },
  methods: {
    removeTask(id) {
      this.todos = this.todos.filter(t => t.id !== id)
    },
    addTask(task){
      this.todos.push(task)
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
