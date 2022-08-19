<template>
  <header class="flex justify-between items-center">
    <h1 class="text-2xl font-bold">{{ title }}</h1>
    <Button
      @toggle-add-task="$emit('toggle-add-task')"
      :text="showAddTask ? 'Close' : 'Add Task'"
      :class="showAddTask ? 'bg-red-600' : 'bg-green-600'"
      class="text-white"
    />
  </header>
</template>

<script>
import Button from "./Button.vue";
export default {
  name: "Header",
  props: {
    title: String,
    showAddTask: Boolean,
  },
  components: {
    Button,
  },
};
</script>
