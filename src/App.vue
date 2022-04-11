<script setup lang="ts">
import NavBar from "./components/NavBar.vue";
</script>

<template>
  <div class="flex h-screen">
    <NavBar />
    <div class="basis-1/2 border-x border-gray-700">Main body</div>
    <div class="grow">aside</div>
  </div>
</template>
