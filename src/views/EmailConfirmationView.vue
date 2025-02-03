<script lang="ts">
import ESCBasicInput from "../components/UI/ESC-basic-input.vue";

export default {
  name: "EmailConfirmationView",
  components: {ESCBasicInput},
  methods: {
    goBack() {
      console.log("goBack");
    }
  },
  data() {
    return {
      emailCode: ""
    }
  }
}
</script>

<template>
  <div class="container">
    <div class="modal_window">
      <div class="header_container">
        <img src="../assets/icons/arrow_left_icon.svg" alt="go_back" class="back_button" @click="goBack"/>
        <h1 class="title">Подтверждение</h1>
      </div>
      <div class="field_block">
        <div class="article">
          На Вашу почту было отправлено письмо с подтверждением. <br> Введите код ниже для завершения регистрации:
        </div>
        <ESCBasicInput class="input_block"
                       :placeholder="'Код подтверждения'"
                       v-model.trim="emailCode"
                       @input="console.log(emailCode)"
        />
      </div>
      <div class="buttons_block">
        <div class="temporary_button">
          <h3>Подтвердить</h3>
        </div>
        <p class="extra_string">Отправить код еще раз</p>
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
  align-content: center;
  gap: 0.75rem;
}

.article {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 85%;
  text-align: center;
  font-size: 90%;
}

.input_block {
  width: 65%;
  height: 2rem;
  text-align: center;
  text-indent: 0;
}

.input_block:active, .input_block:focus {
  text-indent: 0;
  text-align: center;
}

.input_block::placeholder {
  text-align: center;
  text-indent: 0;
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

.extra_string {
  margin: 1% 0 0 0;
  font-size: 80%;
  border-bottom: 1px solid transparent;
  transition-duration: 0.1s;
}

.extra_string:hover {
  border-bottom: 1px solid var(--color-primary);
  cursor: pointer;
}
</style>