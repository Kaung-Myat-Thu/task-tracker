<template>
  <button
    @click="$emit('toggle-add-task')"
    class="font-semibold px-5 py-2 rounded-sm"
  >
    {{ text }}
  </button>
</template>
<script>
export default {
  name: "Button",
  props: {
    text: String,
  },
};
</script>
