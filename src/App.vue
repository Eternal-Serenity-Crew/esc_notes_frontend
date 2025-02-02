<template>
  <div class="app_primary_container">
  </div>
</template>

<script setup lang="ts">

console.log(document.documentElement.clientWidth)
</script>

<style scoped>
.app_primary_container {
  min-height: calc(100vh - 60px);
  display: flex;
  flex-direction: column;
  justify-content: center;
}
</style>