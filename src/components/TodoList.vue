<template>
    <div>
        <ul>
            <TodoItem 
                v-for="todo in todos"
                v-bind:todo="todo"
                v-on:removetodo="removetodo"
            />
        </ul>
    </div>
</template>

<script>

import TodoItem from '@/components/TodoItem'
export default {
    props: ['todos'], 
    components: {
        TodoItem
    },
    methods: {
        removetodo(id){
            alert(id);
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