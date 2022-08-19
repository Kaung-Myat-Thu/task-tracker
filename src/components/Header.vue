<template>
  <header class="flex justify-between items-center">
    <h1 class="text-2xl font-bold">{{ title }}</h1>
    <Button text="Add Task" class="bg-green-600 text-white" />
  </header>
</template>

<script>
import Button from "./Button.vue";
export default {
  name: "Header",
  props: {
    title: String,
  },
  components: {
    Button,
  },
};
</script>
