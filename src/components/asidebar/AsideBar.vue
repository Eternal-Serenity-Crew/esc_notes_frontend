<script setup lang="ts">

import ESCButton from "../UI/esc-button/ESC-button.vue";
import type {openedNote} from "./openedNote";
import {ref} from "vue";
defineProps<{
  openedNotes: openedNote[],
}>();

const isOpen = ref(false)

</script>

<template>
  <div :class="isOpen ? 'aside-bar opened' : 'aside-bar'">
    <div :class="isOpen ? 'nav-group' : 'nav-group closed'">
      <ESCButton
          :btn-style="isOpen ? 'transparent' : 'transparent standalone'"
      >
        ESC admin
      </ESCButton>
      <ESCButton
          btn-style="transparent"
          lead-icon="menu-arrow"
          @click="isOpen = !isOpen; console.log('hi')"
      />
    </div>
    <div class="menu">
      <ESCButton
          lead-icon="home"
          :btn-style="isOpen ? 'transparent' : 'transparent standalone'"
          class="menu-item"
      >
        Главная
      </ESCButton>
      <ESCButton
          lead-icon="chats"
          :btn-style="isOpen ? 'transparent' : 'transparent standalone'"
          class="menu-item"
      >
        Чаты
      </ESCButton>
    </div>
    <div class="separator"></div>
    <div class="opened-notes">
      <ESCButton
          v-for="note in openedNotes"
          :key="note.id"
          lead-icon="opened-note"
          :btn-style="isOpen ? 'transparent' : 'transparent standalone'"
          trail-icon=""
          :href="note.href"
      >
        {{ note.title }}
      </ESCButton>
    </div>
    <ESCButton
        :btn-style="isOpen ? 'inverted' : 'inverted standalone'"
        lead-icon="plus"
        class="new-note"
    >
      Новая заметка
    </ESCButton>
    <div class="auth-buttons">
      <ESCButton
          :btn-style="isOpen ? 'default' : 'default standalone'"
          lead-icon="sign-out"
          class="new-note"
      >
        Выйти
      </ESCButton>
    </div>
  </div>
</template>

<style scoped>
  .aside-bar {
    display: flex;
    flex-direction: column;
    padding: 18px 18px 15px 18px;
    background-color: rgba(196, 172, 172, 0.35);
    border-radius: 25px;
    overflow: hidden;
    width: calc(var(--btn-height) + 2 * var(--v-padding) + 8px);
    transition: width 0.5s;
  }

  .aside-bar.opened {
    width: calc(var(--btn-width) + 24px);
  }

  .nav-group {
    display: flex;
    align-items: center;
    justify-content: space-between;
    user-select: none;
    overflow: hidden;
  }

  .nav-group div:first-child {
    justify-content: flex-start;
  }

  .nav-group.closed div:first-child {
    margin-left: -100%;
  }

  .nav-group div:last-child {
    transform: rotate(180deg);
  }

  .nav-group.closed div:last-child {
    width: var(--btn-height);
    transform: rotate(0);
  }

  .nav-group div {
    color: var(--color-primary);
    font-weight: var(--font-bold);
  }

  .nav-group div:hover, .menu div:hover {
    background-color: transparent;
  }

  .menu div::after {
    content: '';
    position: absolute;
    width: 3px;
    height: 0;
    left: -5px;
    background-color: var(--color-primary);
    transition: height 0.3s;
    border-radius: var(--border-radius-medium);
  }


  .menu .menu-item svg *,
  .menu .menu-item svg {
    stroke: var(--color-primary);
  }

  .menu div:hover::after {
    height: 70%;
  }

  .menu div {
    justify-content: flex-start;
    user-select: none;
    position: relative;
    border-radius: 0;
    gap: var(--icon-text-gap-medium);
  }

  .aside-bar.opened .menu div {
    padding: var(--v-padding);
  }

  .opened-notes {
    display: flex;
    flex-direction: column;
    gap: 0.2vw;
  }

  .opened-notes div {
    justify-content: flex-start;
    gap: 0.8vw;
  }

  .separator {
    height: 0.2vw;
    min-height: 3px;
    border-radius: var(--border-radius-small);
    background-color: var(--color-secondary);
    margin: 1.5vw 0;
  }

  .new-note {
    margin-top: 1vw;
  }


  .auth-buttons {
    margin-top: auto;
    user-select: none;
    display: flex;
    flex-direction: column;
  }
</style>