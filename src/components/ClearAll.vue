<template>
  <button @click="clearAll" class="bg-red-500 mt-2 px-5 ml-5 ...">
    Clear All
  </button>
</template>

<script>
export default {
  name: "ClearAll",
  emits: ['clear-all'],
  methods: {
    clearAll() {
      this.$emit("clear-all");
    },
  },
};
</script>