<template>
  <div
    class="social-card"
    :class="{ 'social-card--used': isUsed }"
    @click="isUsed = true"
  >
    <img :src="social.img" alt="" />
    <p class="social-card__title">{{ social.title }}</p>
    <div class="social-card__foil foil" :class="{ 'foil--used': isUsed }">
      <p class="foil__text">{{ social.foil }}</p>
      <button class="foil__check">
        <img :src="isUsed ? 'icon/check.svg' : 'icon/present.svg'" alt="" />
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "social-card",
  props: {
    social: Object,
  },
  data() {
    return {
      isUsed: false,
    };
  },
};
</script>

<style lang="scss">
.social-card {
  cursor: pointer;
  grid-column: span 4;
  display: flex;
  align-items: center;

  background: #14131e;
  border: 1px solid #28263a;
  border-radius: 10px;
  padding: 10px 20px;

  &--used {
    background: rgba(0, 180, 221, 0.25);
    border: 1px solid #21d4fd;
  }

  &__title {
    font-family: LabGrotesque, serif;
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    color: $color-white;
    padding-left: 15px;
  }

  &__foil {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 7px;
    margin-left: auto;
  }
}

.foil {
  &__text {
    font-family: adineuePROCyr, serif;
    font-style: normal;
    font-weight: bold;
    font-size: 16px;
    color: $color-accent;
    background: gradient-accent(300deg, 35%, 66%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  &__check {
    width: 34px;
    height: 34px;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 50%;
    border: none;
    background: gradient-accent(130deg, 22%, 77%);
  }

  &--used {
    .foil__text {
      color: #b8b1b1;
      background: none;
      -webkit-text-fill-color: unset;
    }

    .foil__check {
      background: rgba(0, 0, 0, 0.4);
    }
  }
}
</style>
