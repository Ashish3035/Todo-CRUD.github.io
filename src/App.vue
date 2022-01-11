<template>
  <!-- <div class="grid place-items-center h-96"> -->
  <h1 class="grid place-items-center text-green-600 text-2xl">To-Do App</h1>
  <AddTodo v-on:add-todo="addTodo" />
  <ClearAll v-on:clear-all="clearAll"/>
  <Todos v-on:delete-todo="deleteTodo(index)" :todos="todos" />
  <!-- </div> -->
</template>
<script>
import Todos from "./components/Todos";
import AddTodo from "./components/AddTodo.vue";
import ClearAll from "./components/ClearAll.vue";
import "./assets/tailwind.css";

export default {
  name: "app",
  components: {
    ClearAll,
    AddTodo,
    Todos,
  },
  data() {
    return {
      todos: [
        {
          id:1,
          title:"todo 1",
        },
        {
          id:2,
          title:"todo 2",
        },
      ],
    };
  },
  methods: {
    addTodo(todo) {
      this.todos = [...this.todos,todo]
    },
    clearAll(){
      this.todos = []
    },
    deleteTodo(index){
      this.todos.splice(index, 1)
    }
  },
};
</script>
<style>
* {
  margin: 10px;
}
body {
  background-color: #27292d;
  color: white;
}
</style>