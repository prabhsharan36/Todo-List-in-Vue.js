<template>
    <div class="todo-items col s12 m6">
            <div class="card blue-grey darken-1">
                <div class="card-content white-text">
                    <span class="card-title">{{todo.title}}</span>
                    <p>{{todo.description}}</p>
                </div>
                <div class="card-action" style="padding: 25px;">
                    <a @click="$emit('del-todo' , todo.id)" href="#" style="float: right; transform: translateY(-50%);">Delete</a>
                </div>
            </div>
    </div>
</template>

<script>

export default {
    props:{ 
        todo:{
        type: Object,
        required: true
        }
    }

    
}
</script>

<style scoped>
    .todo-items {
        background: white;
        padding-left: 0px;
        border-bottom: 1px white dashed;
    }
</style>