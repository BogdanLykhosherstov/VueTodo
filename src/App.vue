<template>
  <div id="app">
    <h1>TodoList</h1>
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from './components/Todos.vue'
import AddTodo from './components/AddTodo.vue'
export default {
  name: 'App',
  components: {
    Todos,AddTodo
  },
  data(){
    return{
      todos:[
        {
          id:1,
          title: "Todo One",
          completed:false
        },
        {
          id:2,
          title: "Todo Two",
          completed:false
        },
        {
          id:3,
          title: "Todo Three",
          completed:false
        },
      ]
    }
  },
  methods:{
    deleteTodo(id){
      this.todos=this.todos.filter(todo => todo.id!=id);
    },
    addTodo(newTodo){
      this.todos = [...this.todos,newTodo];
    }
  }
}
</script>

<style>
*{
  box-sizing: border-box;
  margin:0;
  padding: 0;
}
h1{
  text-align: center;
  padding:10px;
  background: rgb(43, 43, 43);
  color:white;
}
body{
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>
