<script lang="ts">
import TaskHeader from "./TaskHeader.vue";
import Form from "./Form.vue";
import List from "./List.vue";
export default {
  name: "Task",
  components: { TaskHeader, Form, List },
  data() {
    return {
      form: true,
    };
  },
  props: {
    tasks: {
      type: Array,
    },
  },
  emits: ["add-task"],
  methods: {
    handleForm() {
      this.form = !this.form;
    },
    handleAddTask(e: any) {
      this.$emit("add-task", e);
    },
  },
};
</script>

<template>
  <div class="w-2/6 h-auto border-2 rounded-md border-slate-200">
    <TaskHeader @handleForm="handleForm" :form="form" />
    <Form v-if="form" @add-task="handleAddTask" />
    <List
      v-for="tasks in tasks"
      :key="tasks.id"
      :name="tasks.name"
      :date="tasks.date"
      :id="tasks.id"
      @delete-task="$emit('delete-task', tasks.id)"
    />
  </div>
</template>

<style></style>
