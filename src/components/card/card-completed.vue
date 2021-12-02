<template>
  <div class="card-completed">
    <img :src="card.img" alt="" class="card-completed__img" />
    <h3 class="card-completed__title heading heading--card-title2">
      {{ card.title }}
    </h3>
    <p class="card-completed__description">
      {{ card.description }}
    </p>
  </div>
</template>

<script>
export default {
  name: "card-completed",
  props: {
    card: Object,
  },
};
</script>

<style lang="scss">
.card-completed {
  display: flex;
  flex-direction: column;
  gap: 15px;
  &__img {
    border-radius: 7px;
  }

  &__title {
  }

  &__description {
    color: $color-white;
    font-family: LabGrotesque, serif;
    font-size: 16px;
    font-weight: 400;
    font-style: normal;
    line-height: 134%;
    @include tab() {
      font-size: 14px;
    }
  }
}
</style>
