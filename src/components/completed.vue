<template>
  <div class="completed">
    <div class="wrapper grid">
      <h2 class="completed__title heading heading--h2">
        Completed Bounty Hunt & Airdrops
      </h2>
      <CardCompleted
        class="completed__card"
        v-for="(card, k) in cards.slice(0, sliceEnd)"
        :key="k"
        :card="card"
      />
      <button class="completed__btn button button--border">Load more</button>
    </div>
  </div>
</template>

<script>
import CardCompleted from "./card/card-completed";
import { CARDS_COMPLETED } from "../data/CARDS_COMPLETED";
import { isMobile } from "../utils/isMobile";

export default {
  name: "completed",
  data() {
    return {
      cards: CARDS_COMPLETED,
      sliceEnd: 9,
    };
  },
  computed: {},
  mounted() {
    if (isMobile()) {
      this.sliceEnd = 4;
    }
  },
  components: { CardCompleted },
  methods: {
    //TODO добавить метод добавления карточек на кнопку 'Load more'
  },
};
</script>

<style lang="scss">
.completed {
  padding-top: 50px;

  &__title {
    grid-column: span 12;
  }

  &__card {
    grid-column: span 4;
    @include tab() {
      grid-column: span 6;
    }
    @include mob() {
      grid-column: span 12;
    }
  }

  &__btn {
    width: 280px;
    grid-column: span 12;
    justify-self: center;
    @include mob() {
      width: 100%;
    }
  }
}
</style>
