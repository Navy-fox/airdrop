<template>
  <portal to="modal">
    <div class="modal-wrapper">
      <slot></slot>
    </div>
  </portal>
</template>

<script>
export default {
  name: "modal-wrapper",
};
</script>

<style scoped>
.modal-wrapper {
  background: rgba(10, 9, 20, 0.95);
  backdrop-filter: blur(160px);
  display: flex;
  width: 100vw;
  height: 100vh;
  justify-content: center;
  align-items: center;
  position: fixed;
  z-index: 10;
}
</style>
