<template>
  <div
    class="container w-4/5 sm:w-3/6 mx-auto border-2 border-blue-500 rounded-sm h-96 mt-8 p-4"
  >
    <Header title="Task Tracker" />
    <Tasks :tasks="tasks" />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Tasks from "./components/Tasks.vue";
export default {
  name: "App",
  components: {
    Header,
    Tasks,
  },
  data() {
    return {
      tasks: [],
    };
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: "Doctors Appointment",
        day: "March 1st at 1:20pm",
        reminder: false,
      },
      {
        id: 2,
        text: "Meeting with Sara",
        day: "March 10th at 12:00am",
        reminder: false,
      },
      {
        id: 3,
        text: "Food Shopping",
        day: "March 3rd at 8:00am",
        reminder: true,
      },
    ];
  },
};
</script>

<style></style>
