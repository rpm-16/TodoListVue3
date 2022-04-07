<template>
    <div>
        <ul>
            <TodoItem v-for="todoline in todos"
                v-bind:todoelement="todoline"
                v-on:removetodo="removeTodo" />
        </ul>
    </div>
</template>

<script>

import TodoItem from '@/components/TodoItem'
export default {
    props: ['todos'], //include array "todos" from app.vue
    components: {
        TodoItem: TodoItem
    },
    methods: {
        removeTodo(id){
            this.$emit('removetodo', id)
            }
    }
}
</script>

<style scoped>
    ul {
        list-style: none;
        margin: 0;
        padding: 0;
    }
</style>