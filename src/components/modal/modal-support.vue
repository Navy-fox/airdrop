<template>
  <ModalWrapper>
    <transition appear mode="out-in">
      <form action="" key="sup" class="modal-support form-wrapper">
        <img
          src="icon/close.svg"
          class="modal-close"
          alt=""
          @click="CloseModal"
        />
        <h3 class="form-wrapper__title heading heading--h3">Support</h3>
        <div class="fieldset">
          <label class="fieldset__label">Your name</label>
          <input type="text" class="fieldset__input" />
        </div>
        <div class="fieldset">
          <label class="fieldset__label">E-mail</label>
          <input type="email" class="fieldset__input" />
        </div>
        <div class="fieldset">
          <label class="fieldset__label">Your message</label>
          <textarea class="fieldset__input" />
        </div>
        <button
          type="button"
          class="button button--gradient"
          @click="isSuccess"
        >
          Send
        </button>
        <button type="reset" class="button button--border">Cancel</button>
      </form>
    </transition>
  </ModalWrapper>
</template>

<script>
import ModalWrapper from "./modal-wrapper";
import ModalMixin from "../../mixins/modal-mixin";

export default {
  name: "modal-support",
  components: { ModalWrapper },
  mixins: [ModalMixin],
  methods: {
    isSuccess() {
      this.$emit("isSuccess");
    },
  },
  mounted() {
    document.querySelector("body").style.overflow = "hidden";
  },
  destroyed() {
    document.querySelector("body").style.overflow = "auto";
  },
};
</script>

<style lang="scss"></style>
