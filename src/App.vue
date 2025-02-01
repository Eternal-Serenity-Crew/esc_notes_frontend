<template>
  <AsideBar :is-open="true"></AsideBar>
</template>

<script setup lang="ts">
import AsideBar from "./components/AsideBar.vue";
console.log(document.documentElement.clientWidth)
</script>