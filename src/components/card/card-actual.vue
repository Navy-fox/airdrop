<template>
  <div class="card">
    <div class="card__image image">
      <img src="image/card-actual/c1.png" alt="" class="image__bg" />
      <img src="image/card-actual/c1.png" alt="" class="image__front" />
    </div>
    <h3 class="card__title">
      <span class="heading heading--card-title heading--grad2">
        Actual Airdrop title
      </span>
    </h3>
    <p class="card__description">
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Amet beatae
      corporis debitis dignissimos minima molestiae odio odit, quo unde.
    </p>
  </div>
</template>

<script>
export default {
  name: "card-actual",
};
</script>

<style lang="scss">
.card {
  display: flex;
  flex-direction: column;
  gap: 30px;
  &__description {
    font-family: LabGrotesque, serif;
    font-weight: 400;
    font-style: normal;
    font-size: 18px;
    line-height: 140%;
    color: $color-white;
  }
}

.image {
  position: relative;
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
