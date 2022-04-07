<template>
    <li>
    <span v-bind:class="{ done: todoelement.completed }">
        <input type="checkbox" v-on:change="todoelement.completed = !todoelement.completed">
        <strong>{{ todoelement.id }}</strong>
        {{ todoelement.title }}
    </span>
    <button class="btn1" v-on:click="$emit('removetodo',todoelement.id)">&times;</button>
</li>
</template>

<script>
export default {
    props: {
        todoelement: {
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
    border: 1px solid #3f3f3f;
}
.done {
    text-decoration: line-through;
    color: #ccc;
    }
    input {
        margin-right: 1rem;
    }
</style>