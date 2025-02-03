<script setup lang="ts">

</script>

<template>
  <div class="wrapper">
    <h1 class="popup_header">
      <slot name="header">Popup header</slot>
      <img src="../../assets/icons/check_icon.svg" alt="check_icon" class="icon">
    </h1>
    <p class="popup_content">
      <slot name="content">Popup content.</slot>
    </p>
    <div class="temporary_button" @click="$emit('ok')">
      <h3>
        <slot name="ok_button">Button</slot>
      </h3>
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
  scale: 80%;
}

.popup_content {
  margin: 0;
  width: 80%;
  text-align: center;
}

.temporary_button {
  width: 80%;
  height: 2rem;
  background-color: #fff;
  border-radius: 0.5rem;

  display: flex;
  align-items: center;
  justify-content: center;
}

.temporary_button:hover {
  cursor: pointer;
}
</style>