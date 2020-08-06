<template>
  <div id="app" class="elements-padding">
    <TodoList :todos ='todos' v-on:del-todo="deleteTodo" /> 
    <CreateTodo v-on:newTodo="updateData" />
  </div>
</template>

<script>

import TodoList from './components/TodoList'; 
import CreateTodo from './components/CreateTodo'; 

export default {
  name: 'App',
  components: {
    TodoList,
    CreateTodo,
  },
  data() {
    return{
      todos:[ 
        {
          id: 1,
          title: "First Task",
          description: "This is description One"
        },
        {
          id: 2,
          title: "Second Task",
          description: "This is description Two"
        },
        {
          id: 3,
          title: "Third Task",
          description: "This is description Three"
        }
      ],
    
    }
  },
  methods: {
    updateData: function(addTodo){
      this.todos = [...this.todos, addTodo]
    },
    deleteTodo: function(value){
      this.todos = this.todos.filter(todo => todo.id !== value);
    }

  }
}
</script>

<style scoped>

.elements-padding{
  padding: 24px;
}
</style>
