<template>
  <div class="card">
    <div class="card__image image">
      <img :src="card.img" alt="" class="image__bg" />
      <img :src="card.img" alt="" class="image__front" />
    </div>
    <h3 class="card__title">
      <span class="heading heading--card-title heading--grad2">
        {{ card.title }}
      </span>
    </h3>
    <p class="card__description">
      {{ card.description }}
    </p>
  </div>
</template>

<script>
export default {
  name: "card-actual",
  props: {
    card: Object,
  },
};
</script>

<style lang="scss">
.card {
  display: flex;
  flex-direction: column;
  gap: 30px;
  @include mob() {
    gap: 10px;
  }

  &__description {
    font-family: LabGrotesque, serif;
    font-weight: 400;
    font-style: normal;
    font-size: 18px;
    line-height: 140%;
    color: $color-white;
    @include mob() {
      font-size: 14px;
    }
  }
}

.image {
  position: relative;
  width: 100%;

  &__front {
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    border-radius: 7px;
  }

  &__bg {
    filter: blur(40px);
  }
}
</style>
