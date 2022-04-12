<script setup lang="ts">
import { ref } from "vue";
import NavBarButton from "./NavBarButton.vue";
import NavBarButtonChild from "./NavBarButtonChild.vue";

const navBarButtons = ref([
  {
    title: "Dashboard",
    tree: false,
    icon: "bi bi-speedometer2",
    active: false,
    toggleActive: () => {
      return;
    },
    children: null,
  },
  {
    title: "School",
    tree: true,
    icon: "bi bi-building",
    active: false,
    toggleActive: function () {
      this.active = !this.active;
    },
    children: [
      {
        title: "Classes",
        icon: "bi bi-collection",
      },
      {
        title: "Sessions",
        icon: "bi bi-calendar3",
      },
      {
        title: "Periods",
        icon: "bi bi-calendar3",
      },
      {
        title: "Fees",
        icon: "bi bi-cash-coin",
      },
      {
        title: "Branches",
        icon: "bi bi-alt",
      },
      {
        title: "Terms",
        icon: "bi bi-stopwatch",
      },
      {
        title: "Subjects",
        icon: "bi bi-book",
      },
      {
        title: "Teachers",
        icon: "bi bi-person-workspace",
      },
    ],
  },
  {
    title: "Students",
    tree: true,
    icon: "bi bi-mortarboard",
    children: [],
    active: false,
    toggleActive: function () {
      console.log("clicked");
    },
  },
  {
    title: "App",
    tree: true,
    icon: "bi bi-nut",
    children: [],
    active: false,
    toggleActive: function () {
      return;
    },
  },
]);
</script>
<template>
  <nav class="basis-1/6">
    <div class="flex flex-col space-y-16 mx-5 my-5">
      <div>Radiant Minds School</div>
      <ul class="flex flex-col space-y-3">
        <li
          v-for="navBarButton in navBarButtons"
          :key="navBarButton.title"
          v-on:click="navBarButton.toggleActive()"
        >
          <NavBarButton :title="navBarButton.title" :tree="navBarButton.tree">
            <i :class="navBarButton.icon"></i>
          </NavBarButton>
          <ul
            v-if="navBarButton.tree"
            class="flex flex-col space-y-1"
            :class="{ hidden: navBarButton.active }"
          >
            <li
              v-for="navBarButtonChild in navBarButton.children"
              :key="navBarButtonChild.title"
              class="mt-2"
            >
              <NavBarButtonChild :title="navBarButtonChild.title">
                <i :class="navBarButtonChild.icon"></i>
              </NavBarButtonChild>
            </li>
          </ul>
        </li>
      </ul>
    </div>
  </nav>
</template>
