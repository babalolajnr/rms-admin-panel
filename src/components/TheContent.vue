<template>
  <div class="grow border-x border-gray-700">
    <div class="flex justify-between border-b border-gray-700 pl-14 pr-7 py-7">
      <div class="flex space-x-5">
        <i class="bi bi-search font-bold"></i
        ><input
          class="font-bold w-96 bg-transparent outline-none"
          placeholder="Search"
        />
      </div>
      <div>User</div>
    </div>
    <router-view></router-view>
  </div>
</template>
<script setup lang="ts"></script>
