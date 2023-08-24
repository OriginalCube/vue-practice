<template>
  <div class="w-full h-auto flex items-center justify-evenly gap-2 p-4">
    <input
      type="text"
      v-model="text"
      placeholder="Add Task"
      class="rounded-md p-2 text-md bg-slate-800 outline-none border-2 border-slate-200 w-4/6"
    />
    <div class="h-4 w-auto">
      <img
        @click="
          $emit('addTask', {
            name: text,
            id: Math.floor(Math.random() * 100),
            date: new Date().toLocaleDateString(),
          })
        "
        src="/assets/icons/p1.png"
        class="h-full w-auto cursor-pointer"
        alt=""
      />
    </div>
  </div>
</template>

<script lang="ts">
export default {
  name: "Form",
  data() {
    return { text: "" };
  },
};
</script>

<style></style>
