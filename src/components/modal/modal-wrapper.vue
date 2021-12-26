<template>
  <portal to="modal">
    <transition name="modal" appear mode="out-in">
      <div class="modal-wrapper">
        <slot></slot>
      </div>
    </transition>
  </portal>
</template>

<script>
export default {
  name: "modal-wrapper",
};
</script>

<style lang="scss">
.modal-wrapper {
  background: rgba(10, 9, 20, 0.95);
  backdrop-filter: blur(160px);
  display: flex;
  width: 100vw;
  height: 100vh;
  justify-content: center;
  align-items: center;
  position: fixed;
  z-index: 11;

  @include tab() {
    padding: 24px;
  }
}

.modal-enter-active,
.modal-leave-active {
  transition: opacity 1s;
}
.modal-enter,
.modal-leave-to {
  opacity: 0;
}
</style>
