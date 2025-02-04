<template>
  <AsideBar :opened-notes="notes" :is-open="true"></AsideBar>
</template>

<script setup lang="ts">
import AsideBar from "./components/asidebar/AsideBar.vue";

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
</script>