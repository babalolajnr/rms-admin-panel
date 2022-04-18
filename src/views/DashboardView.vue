<template>
  <div class="flex flex-col mx-16 my-8">
    <div class="flex flex-wrap">
      <div
        v-for="card in cards"
        :key="card.title"
        class="cursor-pointer w-60 h-36 rounded-xl ml-3 mt-3 flex items-center justify-center shadow-lg fraudulent-election text-slate-300 group jay-z-hyphen"
      >
        <div class="flex flex-col">
          <span class="text-4xl font-bold text-center group-hover:">
            {{ card.value }}
          </span>
          <span class="text-center group-hover:">
            {{ card.title }}
          </span>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup lang="ts">
import { ref } from "vue";

const cards = ref([
  {
    title: "Students",
    value: "143",
  },
  {
    title: "Teachers",
    value: "21",
  },
  {
    title: "Users",
    value: "4",
  },
  {
    title: "Classrooms",
    value: "9",
  },
  {
    title: "Academic Session",
    value: "2021-2022",
  },
  {
    title: "Term",
    value: "Second",
  },
  {
    title: "Subjects",
    value: "21",
  },
  {
    title: "Alumni",
    value: "2",
  },
]);
</script>
