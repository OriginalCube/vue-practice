<template>
  <div class="w-full text-2xl flex items-center justify-evenly p-2">
    <div class="w-5/6 p-2 flex items-center justify-evenly">
      <p class="text-2xl">{{ name }} {{ date }}</p>
      <img
        src="/assets/icons/p.png"
        class="h-4 w-auto cursor-pointer"
        @click="$emit('delete-task', id)"
        alt=""
      />
    </div>
  </div>
</template>

<script lang="ts">
export default {
  name: "list",
  props: {
    date: String,
    name: String,
    id: Number,
  },
  created() {},
};
</script>

<style></style>
