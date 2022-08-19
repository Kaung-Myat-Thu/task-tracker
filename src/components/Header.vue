<template>
  <header class="flex justify-between items-center">
    <h1 class="text-2xl font-bold">{{ title }}</h1>
    <Button
      v-show="homePage"
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
  computed: {
    homePage() {
      if (this.$route.path === "/") {
        return true;
      } else {
        return false;
      }
    },
  },
};
</script>
