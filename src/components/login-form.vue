<template>
  <form class="login-form form-wrapper">
    <h3 class="heading heading--h3 form-wrapper__title">Enter to account</h3>
    <div class="fieldset">
      <label class="fieldset__label">Enter your E-mail</label>
      <input type="text" class="fieldset__input" />
    </div>
    <div class="fieldset">
      <label class="fieldset__label">Password</label>
      <input type="password" class="fieldset__input" />
    </div>
    <div class="btn-group">
      <button class="button button--gradient" type="button">
        <router-link to="/dashboard">Enter</router-link>
      </button>
      <div class="button-wrap" @click="modals.support = true">
        <button class="button button--grad-border" type="button">
          Support
        </button>
      </div>
      <button class="button button--border btn-pass" type="button">
        Remind me of my password
      </button>
    </div>

    <ModalSupport
      v-model="modals.support"
      v-if="modals.support"
      @isSuccess="
        modals.support = false;
        modals.success = true;
      "
    />
    <ModalSuccess v-model="modals.success" v-if="modals.success" />
  </form>
</template>

<script>
import ModalSuccess from "./modal/modal-success";
import ModalSupport from "./modal/modal-support";

export default {
  name: "login-form",
  components: { ModalSupport, ModalSuccess },
  data() {
    return {
      modals: {
        support: false,
        success: false,
      },
    };
  },
};
</script>

<style lang="scss">
.btn-group {
  grid-column: span 3;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
  margin-top: 20px;

  .button,
  .button-wrap {
    grid-column: span 1;
    width: 100%;
    height: auto;
  }
}

.btn-pass {
  font-family: LabGrotesque, serif;
  font-size: 14px;
  font-style: normal;
  font-weight: 400;
  line-height: 111%;
}
</style>
