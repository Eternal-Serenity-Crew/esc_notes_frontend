<script setup lang="ts">

import ESCButton from "./UI/esc-button/ESC-button.vue";

defineProps<{
  isOpen: boolean;
}>();
</script>

<template>
  <div class="aside-bar" :style="{ width: isOpen ? '17.5vw' : '4.1vw'}">
    <div class="nav-group">
      <h4>ESC admin</h4>
      <ESCButton type="standalone" icon=""/>
    </div>
    <div class="menu">

    </div>
    <div class="separator"></div>
    <div class="opened-notes">

    </div>

    <div class="auth-buttons">
      <ESCButton type="trail">Выйти</ESCButton>
    </div>
  </div>
</template>

<style scoped>
  .aside-bar {
    display: flex;
    flex-direction: column;
    transition: width 0.3s;
    padding: 30px 30px 18px 30px;
    background-color: rgba(196, 172, 172, 0.35);
    border-radius: 25px;
  }
</style>