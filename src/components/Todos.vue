<template>
  <div>
    <div class="to-do-list">
      <h1 class="mt-6 text-xl ...">To-Do List</h1>
      <div class="border-b-4 border-indigo-500 ..."></div>
      <ol class="list-disc">
        <li :key="todo.id" v-for="todo in todos">
          <Todo
            v-bind:todos="todos"
            v-bind:todo="todo"
            v-on:delete-todo="$emit('delete-todo', todo.id)"
          />
        </li>
      </ol>
    </div>
  </div>
</template>
<script>
import Todo from "./Todo.vue";

export default {
  props: ["todos"],
  name: "Todos",
  components: {
    Todo,
  },
};
</script>
<style scoped>
</style>