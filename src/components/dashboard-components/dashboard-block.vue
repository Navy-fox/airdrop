<template>
  <div class="dashboard-block">
    <div class="dashboard-block__title">{{ title }}</div>
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "dashboard-block",
  props: {
    title: {
      type: String,
    },
  },
};
</script>

<style lang="scss">
.dashboard-block {
  background: #141927;
  width: 100%;
  //height: 200px;
  border-radius: 5px;
  border: 1px solid #272c3c;

  &__title {
    display: flex;
    align-items: center;
    justify-content: start;
    padding: 13px 24px;
    background: #1b202f;
    border-bottom: 1px solid #272c3c;
    width: 100%;
    font-family: adineuePROCyr, serif;
    font-size: 18px;
    font-style: normal;
    font-weight: bold;
    line-height: 150%;
    color: $color-white;
  }
}
</style>
