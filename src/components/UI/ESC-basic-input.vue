<script lang="ts">
  export default {
    name: 'ESC-basic-input',
    props: {
      placeholder: String,
      type: {
        type: String,
        default: 'text',
      },
      modelValue: String,
      hasIcon: Boolean,
      icon: {
        type: String,
        default: '',
      },
    },
    methods: {
      getImagePath(imageFileName: string) {
        return new URL(`../../assets/icons/${imageFileName}`, import.meta.url).href;
      }
    }
  }
</script>

<template>
  <input class="input"
         v-if="!hasIcon"
         :placeholder="placeholder"
         :type="type"
         :value="modelValue"
         @input="$emit('update:modelValue', ($event.target as HTMLInputElement).value)"
  />

  <div class="wrapper" v-else>
    <div class="icon_container">
      <img :src="getImagePath(icon)" alt="" class="icon"/>
    </div>
    <input class="input"
           :placeholder="placeholder"
           :type="type"
           :value="modelValue"
           @input="$emit('update:modelValue', ($event.target as HTMLInputElement).value)"
    />
  </div>
</template>

<style scoped>
.wrapper {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  position: relative;
}

.input {
  width: 100%;
  height: 100%;
  border: 1px solid transparent;
  border-radius: 0.5rem;
  transition-duration: 0.2s;
  background-color: var(--background-input-color-primary);
  text-align: left;
  text-indent: 10%;
}

.input::placeholder {
  text-align: left;
  color: rgba(0, 0, 0, 0.7);
  text-indent: 10%;
}

.input:active, .input:focus {
  outline: none;
  border: 1px solid var(--border-color-primary);
  transition-duration: 0.2s;
  text-indent: 10%;
}

.input:hover {
  border: 1px solid var(--border-color-primary);
  transition-duration: 0.2s;
}

.icon_container {
  display: flex;
  justify-content: center;
  align-content: center;
  height: 100%;
  position: absolute;
  left: 0;
  background-color: var(--background-input-color-primary);
  border: 1px solid var(--border-color-primary);
  border-radius: 0.5rem;
}

.icon_container:hover {
  cursor: pointer;
}

.icon {
  scale: 80%;
}
</style>