<script lang="ts">
import ESCBasicInput from "../components/UI/ESC-basic-input.vue";

export default {
  name: "SignUpView",
  components: {ESCBasicInput},
  methods: {
    goBack() {
      console.log("go back");
    }
  },
  data() {
    return {
      username: "",
      email: "",
      password: "",
      repeatPassword: "",
    }
  }
}
</script>

<template>
  <div class="container">
    <div class="modal_window">
      <div class="header_container">
        <img src="../assets/icons/arrow_left_icon.svg" alt="go_back" class="back_button" @click="goBack"/>
        <h1 class="title">Регистрация</h1>
      </div>
      <div class="field_block">
        <ESCBasicInput class="input_block"
                       :has-icon="true"
                       :icon="'person_icon.svg'"
                       :placeholder="'Ваше ФИО'"
                       v-model.trim="username"
                       @input="console.log(username)"
        />
        <ESCBasicInput class="input_block"
                       :has-icon="true"
                       :icon="'at_icon.svg'"
                       :placeholder="'Адрес эл. почты'"
                       v-model.trim="email"
                       @input="console.log(email)"
        />
        <ESCBasicInput class="input_block"
                       :has-icon="true"
                       :icon="'open_eye_icon.svg'"
                       :placeholder="'Пароль'"
                       v-model.trim="password"
                       @input="console.log(password)"
        />
        <ESCBasicInput class="input_block"
                       :type="'text'"
                       :has-icon="true"
                       :icon="'open_eye_icon.svg'"
                       :placeholder="'Подтверждения пароля'"
                       v-model.trim="repeatPassword"
                       @input="console.log(repeatPassword)"
        />
      </div>
      <div class="temporary_button">
        <h3>Вход</h3>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
}

.modal_window {
  background-color: var(--background-color-primary);
  border-radius: 20px;

  min-width: 40vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 2rem;
  padding: 2rem 0;
}

.header_container {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  position: relative;
  height: 3rem;
  width: 100%;
}

.title {
  height: 100%;
  display: flex;
  align-items: center;
}

.back_button {
  display: flex;
  align-items: center;
  position: absolute;
  left: 10px;
  scale: 80%;
  transition-duration: 0.4s;
}

.back_button:hover {
  cursor: pointer;
  scale: 90%;
  transition-duration: 0.4s;
}

.field_block {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 0.75rem;
}

.input_block {
  width: 65%;
  height: 2rem;
}

.temporary_button {
  width: 65%;
  height: 1.75rem;
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