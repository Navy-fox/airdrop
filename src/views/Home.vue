<template>
  <div class="home">
    <Main />
    <Actual />
  </div>
</template>

<script>
// @ is an alias to /src

import Main from "../components/main";
import Actual from "../components/actual";

export default {
  name: "Home",
  components: { Actual, Main },
};
</script>

<style lang="scss"></style>
