<template>
  <div class="home">
    <Main />
    <div class="content">
      <Actual />
      <Completed />
      <Subscribe />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

import Main from "../components/main";
import Actual from "../components/actual";
import Completed from "../components/completed";
import Subscribe from "../components/subscribe";

export default {
  name: "Home",
  components: { Subscribe, Completed, Actual, Main },
};
</script>

<style lang="scss">
.content {
  position: relative;
  background: #0a0914;
  z-index: 2;
}
</style>
