<template>
  <h1>To do aplication</h1>  
  <hr>
  <TodoList 
  v-bind:todos="todos" />
</template>

<script>

import TodoList from '@/components/TodoList'
export default {
  name: 'App',
  data() {
    return {
      todos: [ { id: 1, title: 'Найти удаленку', completed: false},
      { id: 2, title: 'Сделать визу', completed: false},
      { id: 3, title: 'Снять квартиру', completed: false},
      { id: 4, title: 'Выехать из РФ', completed: false}]
    }
  },
  components: {
    TodoList: TodoList
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
