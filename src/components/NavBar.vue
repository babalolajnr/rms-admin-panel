<script setup lang="ts">
import { ref } from "vue";
import NavBarButton from "./NavBarButton.vue";
import NavBarButtonChild from "./NavBarButtonChild.vue";

const schoolState = ref(false);

function toggleSchoolTree() {
  schoolState.value = !schoolState.value;
}
</script>
<template>
  <nav class="basis-1/6">
    <div class="flex flex-col space-y-16 mx-5 my-5">
      <div>Radiant Minds School</div>
      <ul class="flex flex-col space-y-5">
        <li class="">
          <NavBarButton title="Dashboard">
            <i class="bi bi-speedometer2"></i>
          </NavBarButton>
        </li>
        <li class="flex flex-col space-y-2">
          <NavBarButton
            title="School"
            tree="true"
            v-on:click="toggleSchoolTree"
          >
            <i class="bi bi-building"></i>
          </NavBarButton>
          <ul
            class="ml-2 flex flex-col space-y-2 transition-all"
            :class="{ hidden: !schoolState }"
          >
            <li>
              <NavBarButtonChild title="Academic Session">
                <i class="bi bi-calendar3"></i>
              </NavBarButtonChild>
            </li>
            <li>
              <NavBarButtonChild title="Period">
                <i class="bi bi-hourglass-split"></i>
              </NavBarButtonChild>
            </li>
            <li>
              <NavBarButtonChild title="Fee">
                <i class="bi bi-cash-coin"></i>
              </NavBarButtonChild>
            </li>
            <li>
              <NavBarButtonChild title="Classroom">
                <i class="bi bi-collection"></i>
              </NavBarButtonChild>
            </li>
            <li>
              <NavBarButtonChild title="Branches">
                <i class="bi bi-alt"></i>
              </NavBarButtonChild>
            </li>
            <li>
              <NavBarButtonChild title="Terms">
                <i class="bi bi-stopwatch"></i>
              </NavBarButtonChild>
            </li>
            <li>
              <NavBarButtonChild title="Subject">
                <i class="bi bi-book"></i>
              </NavBarButtonChild>
            </li>
            <li>
              <NavBarButtonChild title="Teacher">
                <i class="bi bi-person-workspace"></i>
              </NavBarButtonChild>
            </li>
          </ul>
        </li>
        <li>
          <NavBarButton title="Student" tree="true">
            <i class="bi bi-mortarboard"></i>
          </NavBarButton>
        </li>
        <li>
          <NavBarButton title="App" tree="true">
            <i class="bi bi-nut"></i>
          </NavBarButton>
        </li>
      </ul>
    </div>
  </nav>
</template>
