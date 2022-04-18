<template>
  <div class="grow border-x border-slate-400">
    <TopBar />
    <router-view></router-view>
  </div>
</template>
<script setup lang="ts">
import TopBar from "./TopBar.vue";
</script>
