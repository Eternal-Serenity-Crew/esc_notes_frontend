<script setup lang="ts">

import type {ButtonStyle} from "./types";
import EscIcon from "../icon/esc-icon.vue";
import {useSlots} from "vue";

defineProps<{
  leadIcon?: string,
  trailIcon?: string,
  btnStyle: ButtonStyle,
}>()
</script>

<template>
  <div
      ref="btn"
      :class=" useSlots().default ?
      `btn ${btnStyle}` :
      `btn ${btnStyle} standalone`"
  >
    <div v-if="leadIcon" class="icon-wrap">
      <EscIcon :name="leadIcon"/>
    </div>
    <div class="text">
      <slot></slot>
    </div>
    <div v-if="trailIcon" class="icon-wrap">
      <EscIcon :name="trailIcon"/>
    </div>
  </div>
</template>

<style scoped>
  .btn, .icon-wrap {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .btn {
    padding: var(--v-padding);
    height: var(--btn-height);
    width: var(--btn-width);
    border-radius: var(--border-radius-small);
    font-family: var(--font-family), serif;
    font-weight: var(--font-bold);
    font-size: 16px;
    gap: var(--icon-text-gap-small);
    border: solid 4px transparent;
    transition: all 0.5s;
    text-overflow: clip;
  }

  .btn .fill-current *,
  .btn .fill-current {
    transition: all 0.2s;
  }

  .btn:hover {
    cursor: pointer;
  }

  .icon-wrap {
    min-width: 32px;
    height: 32px;
  }

  .text {
    vertical-align: middle;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    transition: color 0.3s;
    color: var(--color-secondary);
  }

  .standalone {
    width: var(--btn-height);
    padding: var(--v-padding);
    justify-content: center;
    gap: 0;
  }

  .default {
    background-color: var(--color-secondary);
  }

  .default .text {
    color: white;
  }

  .default:hover {
    background-color: var(--color-primary);
  }

  .inverted {
    border-color: var(--color-secondary);
    color: var(--color-secondary);
    background-color: transparent;
    position: relative;
    z-index: 0;
  }

  .inverted::after {
    content: '';
    width: 100%;
    height: 0;
    background-color: var(--color-secondary);
    position: absolute;
    bottom: 0;
    z-index: -1;
    transition: height 0.3s;
    border-radius: 10px;
  }

  .inverted:hover .text {
    color: white;
  }

  .inverted:hover::after {
    height: 100%
  }

  .inverted .fill-current *,
  .inverted .fill-current {
    transition: all 0.2s;
    fill: var(--color-secondary);
  }

  .inverted:hover .fill-current *,
  .inverted:hover .fill-current {
    fill: white;
  }

  .transparent {
    position: relative;
    background-color: transparent;
    fill: var(--color-secondary);
    color: var(--color-secondary);
  }

  .transparent:hover {
    background-color: rgba(9, 36, 68, 0.2);
  }


</style>