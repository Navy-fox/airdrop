<template>
  <div class="menu-mobile"></div>
</template>

<script>
export default {
  name: "menu-mobile",
  methods: {
    closeMobMenu() {
      this.$emit("closeMobMenu");
    },
  },
};
</script>

<style lang="scss">
.menu-mobile {
  width: 80%;
  height: 100%;
  background: #14131e;
  border-radius: 10px 0px 0px 10px;
  border-left: 2px solid #28263a;
  position: fixed;
  top: 0;
  right: 0;
}
</style>
