<template>
  <div
    @dblclick="$emit('toggle-reminder', task.id)"
    :class="[task.reminder ? 'border-l-8 border-green-600' : '']"
    class="my-3 bg-slate-200 rounded-sm px-8 py-4"
  >
    <h3 class="font-semibold text-lg flex items-center justify-between">
      {{ task.text }}
      <i
        @click="$emit('delete-task', task.id)"
        class="fas fa-times font-semibold text-red-700 cursor-pointer"
      ></i>
    </h3>
    <p>{{ task.day }}</p>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: {
    task: Object,
  },
};
</script>
