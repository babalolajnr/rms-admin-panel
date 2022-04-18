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
  },
  {
    title: "App",
    tree: true,
    icon: "bi bi-nut",
    children: [],
    active: false,
  },
]);

let activeNavBarButton = ref();

function toggleActive(index: number) {
  // check if there is an active nav button
  if (activeNavBarButton.value) {
    activeNavBarButton.value.active = false;
  }
  navBarButtons.value[index].active = !navBarButtons.value[index].active;
  activeNavBarButton = ref(navBarButtons.value[index]);
}
</script>
<template>
  <nav class="basis-1/6 shrink-0">
    <div class="flex flex-col space-y-16 mx-5 my-5">
      <div class="text-lg font-bold text-center">Radiant Minds School</div>
      <ul class="flex flex-col space-y-4">
        <li
          v-for="navBarButton in navBarButtons"
          :key="navBarButton.title"
          v-on:click="toggleActive(navBarButtons.indexOf(navBarButton))"
        >
          <NavBarButton
            :title="navBarButton.title"
            :tree="navBarButton.tree"
            :active="navBarButton.active"
          >
            <i :class="navBarButton.icon"></i>
          </NavBarButton>
          <ul
            v-if="navBarButton.tree"
            class="flex flex-col space-y-1 ml-3"
            :class="{ hidden: !navBarButton.active }"
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
