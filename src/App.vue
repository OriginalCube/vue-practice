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
