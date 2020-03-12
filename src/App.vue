<template>
  <div id="app">
    <Header />
    <AddTodo v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />

  </div>
</template>

<script>
import Header from './components/layout/appHeader';
import AddTodo from './components/layout/AddTodo';
import Todos from './components/Todos';


export default {
  name: 'App',
  components: {
    Todos,
    Header,
    AddTodo
    
  },
  data(){
    return {
      todos : [
        {
          id : 1,
          title : "This is one",
          completed : false
        },
        {
          id : 2,
          title : "This is two",
          completed : true
        },
        {
          id : 3,
          title : "This is three",
          completed : false
        }
      ]
    }
  },
  methods: {
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo){
      this.todos = [...this.todos, newTodo];
    }
  }
}
</script>

<style>
*{
  margin:0;
  padding:0;
}
body{
  font-family:Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
.btn{
  border: none;
  background: #555;
  color: #fff;
  cursor: pointer;
  padding: 5px 5px;
}
.btn:hover{
  background: #fff;
  color: #555;
}
</style>
