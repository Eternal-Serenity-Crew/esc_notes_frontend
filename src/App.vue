<template>
  <div class="app_primary_container">
    <AsideBar :opened-notes="notes"/>
    <div class="app_container">
      <SignUpView/>
    </div>
  </div>
</template>

<script setup lang="ts">

import AsideBar from "./components/asidebar/AsideBar.vue";
import SignUpView from "./views/SignUpView.vue";

const notes = [
  {
    id: 1,
    title: "Линал Теормин fasdfsdaf",
    href: "https://vk.com"
  },
  {
    id: 2,
    title: "Матан Теормин",
    href: "https://vk.com"
  },
  {
    id: 3,
    title: "Линал Коллок",
    href: "https://vk.com"
  },
  {
    id: 4,
    title: "Кринж",
    href: "https://vk.com"
  }
]

console.log(document.documentElement.clientWidth)
</script>

<style scoped>
.app_primary_container {
  min-height: calc(100vh - 60px);
  display: grid;
  grid-template-columns: auto 9fr;
}

.app_container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border: 1px solid red;
}
</style>
