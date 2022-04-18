<template>
  <div class="grow border-x border-gray-700">
    <TopBar />
    <router-view></router-view>
  </div>
</template>
<script setup lang="ts">
import TopBar from "./TopBar.vue";
</script>
