<template>
  <form @submit.prevent="onSubmit">
    <div class="my-3">
      <label class="font-semibold text-lg block mb-2">Task</label>
      <input
        class="border border-gray-500 px-5 py-2 w-full rounded-sm"
        type="text"
        name="text"
        v-model="text"
        placeholder="Enter Task"
      />
    </div>
    <div class="my-3">
      <label class="font-semibold text-lg block mb-2">Day & Time</label>
      <input
        class="border border-gray-500 px-5 py-2 w-full rounded-sm"
        type="text"
        name="day"
        v-model="day"
        placeholder="Enter day and time"
      />
    </div>
    <div class="my-3 grid grid-cols-3 items-center">
      <label class="font-semibold text-lg grid-cols-1" for="reminder"
        >Reminder</label
      >
      <input
        class="w-4 h-4 cursor-pointer"
        type="checkbox"
        name="reminder"
        v-model="reminder"
        id="reminder"
      />
    </div>
    <div class="my-3">
      <input
        class="text-center w-full bg-black text-white rounded-sm py-2 font-mono cursor-pointer"
        type="submit"
        value="Save Task"
      />
    </div>
  </form>
</template>

<script>
export default {
  name: "AddTask",
  data() {
    return {
      text: "",
      day: "",
      reminder: false,
    };
  },
  methods: {
    onSubmit() {
      if (!this.text) {
        alert("Please add a task");
        return;
      }
      const newTask = {
        // id: Math.floor(Math.random() * 1000),
        text: this.text,
        day: this.day,
        reminder: this.reminder,
      };

      this.$emit("add-task", newTask);
      this.text = "";
      this.day = "";
      this.reminder = false;
    },
  },
};
</script>
