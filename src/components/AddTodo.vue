<template>
    <form @submit.prevent="onSubmit">
        <input type="text" v-model="title">
        <button type="submit">Create</button>
    </form>   
</template>

<script>
export default {
    data(){
        return {
            title: ''
        }
    },
    methods: {
        onSubmit() {
            //console.log('Submit', this.title);
            if(this.title.trim()) {
                const newTodo = {
                    id: Date.now(),
                    title: this.title,
                    completed: false
                }
                this.$emit('add-todo', newTodo)
                this.title =''
            }
        },
        removeTodo(id){
            this.todos=this.todos.filter(t => t.id !== id)
        }
    }
}
</script>

<style scoped>
input {
    margin: 1rem;
    }
</style>