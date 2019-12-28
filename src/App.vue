<template>
  <div id="app">
    <Header />
    <AddTodo v-on:add-todo='addTodo' />
      <ToDo :todos="todos" v-on:del-todo="deleteTodo" />
   
  </div>
</template>

<script>
import Header from './components/Header/Header';
import ToDo from './components/ToDo';
import AddTodo from './components/AddTodo';

export default {
  name: 'app',
  components: {
    ToDo,
    Header,
    AddTodo
  },
  data ()
  {
    return {
      todos: [
        {
          id: 1,
          title: "TODO 1",
          completed: false
        },
         {
          id: 2,
          title: "TODO 2",
          completed: true
        },
         {
          id: 3,
          title:" TODO 3",
          completed: false
        }
      ]
    }
  },
  methods:{
    deleteTodo(id) {
      this.todos=this.todos.filter(todo => todo.id !=id);
    },
    addTodo(newTodo){
      this.todos=[...this.todos, newTodo];
    }
  }
}
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
  .btn {
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }
  .btn:hover {
    background: #666;
  }
</style>
