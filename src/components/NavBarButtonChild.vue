<script setup lang="ts">
defineProps<{
  title: string;
}>();
</script>
<template>
  <button
    class="rounded-xl px-4 py-3 bg-green-700 w-full text-left flex space-x-3 text-sm hover:bg-opacity-70 hover:translate-x-2 transition-all"
  >
    <slot />
    <span>{{ title }}</span>
  </button>
</template>
<style>
@import "bootstrap-icons/font/bootstrap-icons.css";
</style>
