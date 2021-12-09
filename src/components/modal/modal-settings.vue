<template>
  <modal-wrapper>
    <form class="modal-settings modal-body">
      <h3 class="modal-settings__title heading heading--h3">
        Settings profile
      </h3>
      <div class="fieldset">
        <label class="fieldset__label">Your name</label>
        <input type="text" class="fieldset__input" />
      </div>
      <div class="fieldset">
        <label class="fieldset__label">Your city</label>
        <input type="text" class="fieldset__input" />
      </div>
      <div class="fieldset">
        <label class="fieldset__label">Phone number</label>
        <input type="tel" class="fieldset__input" />
      </div>
      <div class="fieldset">
        <label class="fieldset__label">E-mail</label>
        <input type="email" class="fieldset__input" />
      </div>
      <div class="fieldset">
        <label class="fieldset__label">Wallet Foil</label>
        <input type="text" class="fieldset__input" />
      </div>
      <div class="collaboration">
        <div class="fieldset">
          <label class="fieldset__label">Google</label>
          <button type="button" class="fieldset__button">v</button>
        </div>
        <div class="fieldset">
          <label class="fieldset__label">Telegram</label>
          <button type="button" class="fieldset__button">v</button>
        </div>
        <div class="fieldset">
          <label class="fieldset__label">Facebook</label>
          <button type="button" class="fieldset__button">v</button>
        </div>
        <div class="fieldset">
          <label class="fieldset__label">Linkedin</label>
          <button type="button" class="fieldset__button">v</button>
        </div>
      </div>
      <div class="separator"></div>
      <button class="button button--gradient">Save settings</button>
      <div class="button-wrap">
        <button class="button button--grad-border">Support</button>
      </div>
      <button class="button button--gradient">Cancel</button>
    </form>
  </modal-wrapper>
</template>

<script>
import ModalWrapper from "./modal-wrapper";

export default {
  name: "modal-settings",
  components: { ModalWrapper },
  mounted() {
    document.querySelector("body").style.overflow = "hidden";
  },
  destroyed() {
    document.querySelector("body").style.overflow = "auto";
  },
};
</script>

<style lang="scss">
.modal-settings {
  &__title {
    grid-column: span 3;
  }

  .button,
  .button-wrap {
    grid-column: span 1;
    width: 100%;
    height: auto;
  }
}

.collaboration {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-column: span 3;
  gap: 10px;

  .fieldset {
    grid-column: span 1;
  }
}

.separator {
  grid-column: span 3;
  width: 100%;
  height: 1px;
  background: #257b8e;
}
</style>
