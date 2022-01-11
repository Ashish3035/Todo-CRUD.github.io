<template>
  <label class="block">
    <span
      class="
        after:content-['*'] after:ml-0.5 after:text-red-500
        block
        text-xl
        font-medium
        text-gray-1000
      "
    >
      New To-Do
    </span>
    <input
      type="text"
      name="text"
      class="
        mt-1
        px-3
        py-2
        bg-black
        border
        shadow-sm
        border-gray-300
        placeholder-gray-1000
        focus:outline-none focus:border-sky-500 focus:ring-sky-500
        block
        w-full
        rounded-md
        focus:ring-1
      "
      v-model="title"
    />
  </label>
  <button @click="storeData" class="bg-indigo-500 mt-2 px-5 ...">
    Add ToDo
  </button>
</template>

<script>
export default {
  name: "AddTodo",
  emits: ["add-todo"],
  data() {
    return {
      title: "",
    };
  },
  methods: {
    storeData() {
      const newTodo = {
        id: Date.now(),
        title: this.title,
      };
      this.$emit("add-todo", {
        newTodo,
      });
      this.title = "";
    },
  },
};
</script>