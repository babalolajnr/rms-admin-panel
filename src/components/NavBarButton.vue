<script setup lang="ts">
const props = defineProps({
  title: String,
  tree: {
    type: Boolean,
    default: false,
    required: false,
  },
  treeOpen: {
    type: Boolean,
    default: false,
    required: false,
  },
});
</script>
<template>
  <button
    class="rounded-xl px-4 py-4 w-full text-left flex justify-between font-bold transition-all"
    :class="{ 'bg-[#33b18a]': treeOpen, 'hover:bg-[#33b1895d]': !treeOpen }"
  >
    <div class="flex space-x-3">
      <slot />
      <span>{{ title }}</span>
    </div>
    <div v-if="tree">
      <i
        class="bi"
        :class="{ 'bi-caret-left': !treeOpen, 'bi-caret-down': treeOpen }"
      ></i>
    </div>
  </button>
</template>
<style>
@import "bootstrap-icons/font/bootstrap-icons.css";
</style>
