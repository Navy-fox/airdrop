<template>
  <ModalWrapper>
    <div class="modal-success modal-body">
      <img src="icon/close.svg" class="modal-close" alt="" />
      <div class="modal-success__success">
        <Success />
      </div>
      <h3 class="modal-success__description heading">Success</h3>
    </div>
  </ModalWrapper>
</template>

<script>
import ModalWrapper from "./modal-wrapper";
import Success from "../icon/success";

export default {
  name: "modal-success",
  components: { Success, ModalWrapper },
  mounted() {
    document.querySelector("body").style.overflow = "hidden";
  },
  destroyed() {
    document.querySelector("body").style.overflow = "auto";
  },
};
</script>

<style lang="scss">
.modal-success {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 500px;
  padding: 60px;
  gap: 30px;
  &__description {
    font-size: 52px;
    @include mob() {
      font-size: 32px;
    }
  }
  &__success {
    border: 1px solid #21fda1;
    padding: 65px 60px;
    border-radius: 50%;
  }
}
</style>
