<template>
  <div id="app">
    <Header/>
    <todoAdd v-on:todo:add="addTodo"/>
    <todoItems v-for="todo in todos" v-bind:todo="todo" v-on:todo:remove="removeTodo"/>
  </div>
</template>

<script>
import Header from './components/todoTitle.vue'
import todoAdd from './components/todoAdd.vue'
import todoItems from './components/todoItems.vue'

export default {
  name: 'App',
  components: {
    Header,
    todoAdd,
    todoItems
  },
  data(){
    return{
      todos:[],
      nextId:1,
    }
  },
  methods:{
    addTodo(item){
      this.todos.push({id:this.nextId,name:item});
      this.nextId++;
    },

    removeTodo(id){
      let todos=this.todos;
      this.todos=todos.filter((todo)=>todo.id!=id);
    }
  }

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top:5%;
  margin-left:20%;
  margin-right:20%;
  border:1px solid lightgreen;
  padding: 5%;
}
</style>
