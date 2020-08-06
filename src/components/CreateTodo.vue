<template>
    <div>
        <input type="text" v-model="todoTitle" placeholder="Add Todo..." >
        <input type="text" v-model="todoDescription" placeholder="Add description..." >
        <button data-v-c2258edc="" class="btn waves-effect waves-light" style="float: left;">Submit</button>
    </div>
</template>


<script>

import uuid from 'uuid';

export default {
    data(){
        return{
            todoTitle:'',
            todoDescription:''
        }
    },
    methods: {
        sendData: function(){
             const addTodo={
                id: uuid.v4(),
                title: this.todoTitle,
                description: this.todoDescription
            }
            this.$emit('newTodo', addTodo)
            this.todoTitle = ""
            this.todoDescription = ""
        }
    }
}
</script>


<style scoped>

</style>