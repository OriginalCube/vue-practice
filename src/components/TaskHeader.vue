<script lang="ts">
export default {
  name: "TaskHeader",
  props: {
    form: Boolean,
  },
};
</script>

<template>
  <div class="w-full h-auto p-2 flex items-center justify-around">
    <p class="text-5xl">Track Activity</p>
    <button
      @click="$emit('handleForm')"
      class="text-slate-800 bg-slate-200 border-2 border-slate-200 p-2 rounded-md font-semibold px-4"
    >
      {{ form ? "Close" : "Add Task" }}
    </button>
  </div>
</template>

<style></style>
