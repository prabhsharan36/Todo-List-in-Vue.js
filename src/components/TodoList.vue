<template>
    <div class="row">
        <div v-for="todo in todos" :key ="todo.id">
            <TodoItem :todo='todo' v-on:del-todo="$emit('del-todo', todo.id)"/>
        </div>
    </div>
</template>

<script>

import TodoItem from './TodoItem.vue';

export default {
    components:{
        TodoItem
    },
    props:{
        todos: {
            type: Array,
            required: true
        }
    }
}
</script>

<style scoped>

</style>