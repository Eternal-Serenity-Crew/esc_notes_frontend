<script setup lang="ts">

import type {ButtonStyle, ButtonType} from "./types";

  defineProps<{
    type: ButtonType,w
    style: ButtonStyle,
    icon: string,
  }>();

</script>

<template>
  <div class="btn" :class="type">
    <div v-if="type === 'lead'"><img src="" alt=""></div>
    <div v-if="type !== 'standalone'"><slot></slot></div>
    <div v-else><img src="" alt="" ></div>
    <div v-if="type === 'trail'"><img src="" alt=""></div>
  </div>
</template>

<style scoped>
  .btn {
    display: flex;
    justify-content: center;
    padding: var(--v-padding) var(--h-padding);
    background-color: var(--color-secondary);
    border-radius: var(--border-radius-small);
    font-family: var(--font-family), serif;
    font-weight: var(--font-semi-bold);
    font-size: 16px;
    outline: none;
    border: none;
  }

  .standalone {
    width: 2.3vw;
    aspect-ratio: 1/1;
    padding: var(--v-padding);
  }
</style>