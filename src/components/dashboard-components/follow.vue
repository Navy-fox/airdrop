<template>
  <div class="follow wrapper">
    <h2 class="follow__title heading heading--h2">Follow on social network</h2>
    <div class="follow__social-networks grid">
      <SocialCard v-for="(i, k) in social" :key="k" :social="i" />
    </div>
  </div>
</template>

<script>
import SocialCard from "./social-card";
import { CARDS_SOCIAL } from "../../data/CARDS_SOCIAL";

export default {
  name: "follow",
  components: { SocialCard },
  data() {
    return {
      social: CARDS_SOCIAL,
    };
  },
};
</script>

<style lang="scss">
.follow {
  padding-top: 130px;
  padding-bottom: 80px;
  .grid {
    row-gap: 10px;
  }

  &__title {
    padding-bottom: 40px;
  }
}
</style>
