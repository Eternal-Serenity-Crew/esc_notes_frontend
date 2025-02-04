<script setup lang="ts">

</script>

<template>
  <div class="wrapper">
    <h1 class="popup_header">
      <slot name="header">Popup header</slot>
      <img src="../../assets/icons/danger_icon.svg" alt="check_icon" class="icon">
    </h1>
    <p class="popup_content">
      <slot name="content">Popup content.</slot>
    </p>
    <div class="buttons_block">
      <div class="temporary_button" @click="$emit('cancel')">
        <h3><slot name="cancel_button">Button</slot></h3>
      </div>
      <div class="temporary_button danger_button" @click="$emit('ok')">
        <h3><slot name="ok_button">Button</slot></h3>
      </div>
    </div>
  </div>
</template>

<style scoped>
.wrapper {
  width: 40%;
  background-color: var(--popup-background-color);
  border-radius: 1rem;
  border: 2px solid var(--popup-border-color);
  padding: 1rem;

  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  gap: 1.5rem;
}

.popup_header {
  margin: 0;
  display: flex;
  flex-direction: row-reverse;
  justify-content: center;
  align-items: center;
}

.icon {
  scale: 70%;
}

.popup_content {
  margin: 0;
  width: 80%;
  text-align: center;
}

.buttons_block {
  width: 90%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
}

.temporary_button {
  width: 80%;
  height: 2rem;
  background-color: rgba(9, 36, 68, 0.75);
  border-radius: 0.5rem;

  display: flex;
  align-items: center;
  justify-content: center;
}

.temporary_button:hover {
  cursor: pointer;
}

.danger_button {
  border: 2px solid rgba(9, 36, 68, 0.75);
  background-color: rgba(255, 255, 255, 0.75);
}

.temporary_button > h3 {
  color: white;
}

.danger_button > h3 {
  color: rgba(9, 36, 68, 0.75);
}
</style>