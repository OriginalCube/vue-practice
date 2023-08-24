<template>
  <div
    class="bg-slate-800 text-white w-full h-auto p-4 flex items-center justify-center"
  >
    <Task :tasks="tasks" @delete-task="deleteTask" @add-task="addTask" />
  </div>
</template>

<script lang="ts">
import Task from "./components/Task.vue";

interface TaskProps {
  // Stil no notes regarding using interface / props in vue when using TS
  // Template can be considered the "JSX" equivalent of vue
  // Scripts are where you write all of the JS functions/states
  // style while on the other hand is the internal css provided by vue
  // More details on export default
  // Name is what will be used in referencing the component
  // Data is a function where you can store the states that will be used all throughout the program cycle
  // Emits is how we transfer data from child to parent
  // Created is an on mount function I think?
  // Methods is an object where you can store the functions that will be used or referenced for emits

  // All in all, vue is a great framework but I'll need to study which libraries from react can be easily be used in vue as well.
  // This could be easier if it was done using JS to prevent "any" requirements that are hard to fix.

  id: Number;
  name: String;
  date: String;
}

export default {
  name: "App",
  components: {
    Task,
  },
  data() {
    return {
      tasks: [
        {
          id: 1,
          name: "Running",
          date: new Date().toLocaleDateString(),
        },
        {
          id: 2,
          name: "Jogging",
          date: new Date().toLocaleDateString(),
        },
      ],
    };
  },
  methods: {
    deleteTask(id: number) {
      this.tasks = this.tasks.filter((task) => task.id !== id);
    },
    addTask(e: any) {
      this.tasks = [...this.tasks, e];
    },
  },
};
</script>
