<template>
  <div>
    <p>{{ todo.title }}</p>
    <button
      @click="edit"
      class="bg-yellow-800 text-indigo-200 mt-2 px-5 mx-px ..."
    >
      Edit
    </button>
    <button
      @click="$emit('delete-todo', todo.id)"
      class="bg-yellow-800 text-indigo-200 mt-2 px-5 mx-px ..."
    >
      Remove
    </button>
    <div v-if="this.input">
      <div class="w-full max-w-xs">
        <form
          @submit="updateTodo"
          class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4"
        >
          <div class="mb-4">
            <input
              class="
                shadow
                appearance-none
                border
                rounded
                w-full
                py-2
                px-3
                text-gray-700
                leading-tight
                focus:outline-none focus:shadow-outline
              "
              type="text"
              v-model="updatedTodo"
            />
          </div>

          <div class="flex items-center justify-between">
            <button
              class="
                bg-blue-500
                hover:bg-blue-700
                text-white
                font-bold
                py-2
                px-4
                rounded
                focus:outline-none focus:shadow-outline
              "
              type="button"
            >
              Update
            </button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Todo",
  props: ["todo", "todos"],
  data() {
    return {
      input: false,
      updatedTodo: "",
    };
  },
  methods: {
    edit() {
      this.input = !this.input;
    },
    updateTodo() {
      this.todos.filter((todo) => {
        if (todo.id == this.todo.id) {
          todo.todo = this.updatedTodo;
        }
      });
      this.input = false;
    },
  },
};
</script>
<style scoped>
</style>