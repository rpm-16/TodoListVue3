<template>
  <h1>To do aplication</h1>  
  <AddTodo 
    @add-todo="addTodo" />

  <TodoList v-bind:todos="todos"
  @removetodo="removeTodo"
  />
</template>

<script>
import TodoList from '@/components/TodoList' //импортируем компонент @указывает в папку сорсе всегда
import AddTodo from '@/components/AddTodo' 
export default {
  name: 'App',
  data() {
    return {
      todos: [ { id: 1, title: 'Найти удаленку', completed: false},
        { id: 2, title: 'Сделать визу', completed: false},
        { id: 3, title: 'Снять квартиру', completed: false},
        { id: 4, title: 'Выехать из РФ', completed: false}
      ]
    }
  },
  components: {
    TodoList: TodoList, // registration of components key: value
    AddTodo: AddTodo
  },
  methods: {
    // onSubmit() {
    //   console.log('Submit');
    // },
    removeTodo(id){
      this.todos=this.todos.filter(t => t.id !== id)
    },
    addTodo(todo) {
      this.todos.push(todo)
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
