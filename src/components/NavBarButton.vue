<script setup lang="ts">
const props = defineProps({
  title: String,
  tree: {
    type: Boolean,
    default: false,
    required: false,
  },
  active: {
    type: Boolean,
    default: false,
    required: false,
  },
});
</script>
<template>
  <button
    class="rounded-xl px-4 py-3 w-full text-left flex justify-between text-sm hover:bg-opacity-70 hover:translate-x-2 transition-all"
    :class="{ 'bg-[#33b18a]': active }"
  >
    <div class="flex space-x-3">
      <slot />
      <span>{{ title }}</span>
    </div>
    <div v-if="tree">
      <i
        class="bi"
        :class="{ 'bi-caret-left': active, 'bi-caret-down': !active }"
      ></i>
    </div>
  </button>
</template>
<style>
@import "bootstrap-icons/font/bootstrap-icons.css";
</style>
