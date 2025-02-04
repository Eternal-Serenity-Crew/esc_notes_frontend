<script lang="ts">
import ESCBasicInput from "../components/UI/ESC-basic-input.vue";

export default {
  name: "LoginView",
  components: {ESCBasicInput},
  methods: {
    goBack() {
      console.log("goBack");
    }
  },
  data() {
    return {
      email: "",
      password: "",
    }
  }
}
</script>

<template>
  <div class="container">
    <div class="modal_window">
      <div class="header_container">
        <img src="../assets/icons/arrow_left_icon.svg" alt="go_back" class="back_button" @click="goBack"/>
        <h1 class="title">Вход в аккаунт</h1>
      </div>
      <div class="field_block">
        <ESCBasicInput class="input_block"
                       :has-icon="true"
                       :icon="'at_icon.svg'"
                       :placeholder="'Адрес эл. почты'"
                       v-model.trim="email"
                       @input="console.log(email)"
        />
        <ESCBasicInput class="input_block"
                       :type="'password'"
                       :has-icon="true"
                       :icon="'open_eye_icon.svg'"
                       :placeholder="'Пароль'"
                       v-model.trim="password"
                       @input="console.log(password)"
        />
      </div>
      <div class="buttons_block">
        <div class="temporary_button">
          <h3>Вход</h3>
        </div>
        <p class="no_account_title">У меня еще нет аккаунта</p>
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
  justify-content: center;
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

.buttons_block {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
  align-items: center;
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

.no_account_title {
  margin: 1% 0 0 0;
  font-size: 80%;
  border-bottom: 1px solid transparent;
  transition-duration: 0.1s;
}

.no_account_title:hover {
  border-bottom: 1px solid var(--color-primary);
  cursor: pointer;
}
</style>