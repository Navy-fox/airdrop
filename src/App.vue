<template>
  <div id="app">
    <portal-target name="modal"></portal-target>
    <Header
      :style="`background-color: rgba(10, 9, 20, ${isScroll})`"
      @scroll="onScroll"
    />
    <router-view />
  </div>
</template>

<script>
import Header from "./components/header";

export default {
  components: { Header },
  data() {
    return {
      isScroll: 0.5,
    };
  },
  methods: {
    onScroll(e) {
      const scrollTop = e.target.scrollingElement.scrollTop;
      if (scrollTop >= window.innerHeight / 2) {
        this.isScroll = scrollTop / window.innerHeight;
      }
    },
  },
  mounted() {
    window.addEventListener("scroll", this.onScroll);
  },
  destroyed() {
    window.removeEventListener("scroll", this.onScroll);
  },
};
</script>

<style lang="scss">
#app {
  background-color: $color-dark;
  min-height: 100vh;
}

.scroll {
  background: rgba(10, 9, 20, 1);
}
</style>
