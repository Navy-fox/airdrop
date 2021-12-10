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
    <button class="button button--gradient" type="button">Enter</button>
    <div class="button-wrap">
      <button class="button button--grad-border" type="button">Support</button>
    </div>
    <button class="button button--border btn-pass" type="button">
      Remind me of my password
    </button>
  </form>
</template>

<script>
export default {
  name: "login-form",
};
</script>

<style lang="scss">
.btn-pass {
  font-family: LabGrotesque, serif;
  font-size: 14px;
  font-style: normal;
  font-weight: 400;
  line-height: 111%;
}
</style>
