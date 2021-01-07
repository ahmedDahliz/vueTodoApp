<template>
 <div id="app">
  
   <AddTodo v-on:add-todo="addTodo"/>
   <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
 </div>
</template>

<script>
import AddTodo from '../components/AddTodo';
import Todos from '../components/Todos';
import axios from "axios";
export default {
  name: 'Home',
  components: {
    Todos,
    AddTodo,
  },
  data(){
    return {
      todos: []
    }
  },
  methods: {
    deleteTodo(id){
      axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
      .then(()=>{
        this.todos = this.todos.filter(todo => todo.id !== id);
      })
      .catch(err => console.log(err));
      
    },
    addTodo(title){
      axios.post('https://jsonplaceholder.typicode.com/todos', {
        title,
        completed: false
      }).then(todo=>{
       this.todos = [...this.todos, todo.data];
      })
      .catch(err => console.log(err));
      
    },
  },
  created() {
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5')
    .then(todos=>{
      this.todos = todos.data
    })
    .catch(err => console.log(err));
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
