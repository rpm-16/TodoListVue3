<template>
    <li v-bind:class="{ done: todo.completed }">
    <span>
        <input type="checkbox" v-on:change="todo.completed = !todo.completed">
        <strong>{{ todo.id }}</strong>
        {{ todo.title }}
    </span>
    <button class="btn1" v-on:click="$emit('removetodo',todo.id)">&times;</button>
</li>
</template>

<script>
export default {
    props: {
        todo: {
            type: Object,
            required: true
        },
    }
}
</script>

<style scoped>
li {
    border: 1px solid #3f3f3f;
    display: flex;
    justify-content: space-between;
    padding: .5rem 2rem;
    margin-bottom: 1rem;
}
.btn1 {
    background: red;
    color: white;
    font-weight: bold;
}
.done {
    text-decoration: line-through;
    color: #ccc;
    }
</style>