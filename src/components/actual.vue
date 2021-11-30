<template>
  <div class="actual">
    <div class="wrapper grid">
      <div class="logo-circle">
        <img src="icon/logo-circle.svg" alt="" class="logo-circle__icon" />
        <img src="icon/logo-circle.svg" alt="" class="logo-circle__bg" />
      </div>
      <div class="info">
        <p class="info__text">
          Test the FOIL NFT storage, send and receive encrypted messages,
          transactions and save NFT content over blockchain and bring the crypto
          benchmark tests of FOIL Network live! 1,250,000 FOIL are reserved for
          the crypto airdrop and bounty participants.
        </p>
        <h2 class="info__title heading heading--h2 heading--grad2">
          <span class="heading heading--h2">
            Join FOIL Blockchain Interactions and earn FOIL crypto.
          </span>
        </h2>
        <button class="info__but button button--circle">
          <img src="icon/arrow.svg" class="info__arrow" alt="" />
        </button>
      </div>
      <CardActual
        v-for="(card, k) in cards"
        :key="k"
        class="actual__card"
        :card="card"
      />
    </div>
    <div class="line"></div>
  </div>
</template>

<script>
import CardActual from "./card/card-actual";
import { CARDS_ACTUAL } from "../data/CARDS_ACTUAL";
export default {
  name: "actual",
  data() {
    return {
      cards: CARDS_ACTUAL,
    };
  },
  components: { CardActual },
};
</script>

<style lang="scss">
.actual {
  display: flex;
  flex-direction: column;
  gap: 40px;
  position: relative;
  //background: #0a0914;
  padding-top: 60px;
  //z-index: 2;

  &__card {
    grid-column: span 6;
    @include tab() {
      grid-column: span 12;
    }
  }
}

.logo-circle {
  grid-column: span 6;
  position: relative;
  align-self: center;
  justify-self: center;
  @include lap() {
    grid-column: span 4;
  }
  @include tab() {
    grid-column: span 12;
  }

  &__icon {
    position: absolute;
    left: 112px;
    top: 112px;
    width: 167px;
    height: 167px;
  }

  &__bg {
    width: 391px;
    height: 391px;
    filter: blur(40px);
    opacity: 0.38;
  }
}

.info {
  grid-column: span 6;
  display: grid;
  grid-template-columns: 1fr 140px;
  grid-template-rows: 130px 1fr;
  column-gap: 20px;
  row-gap: 30px;
  @include lap() {
    grid-column: span 8;
  }
  @include tab() {
    grid-column: span 12;
  }
  @include mob() {
    grid-template-columns: 1fr 60px;
    column-gap: 10px;
  }

  &__text {
    font-family: LabGrotesque, serif;
    font-style: normal;
    font-weight: 400;
    font-size: 18px;
    line-height: 171%;
    color: $color-white;
    grid-column: 1/3;
    @include mob() {
      font-size: 14px;
    }
  }

  &__title {
    grid-column: 1/2;
  }

  &__but {
    width: 140px;
    height: 140px;
    grid-column: 2/3;
    @include mob() {
      width: 60px;
      height: 60px;
    }
  }

  &__arrow {
    margin: auto;
    transform: rotate(90deg);
    width: 20px;
  }
}

.line {
  width: 80%;
  height: 1px;
  margin: auto;
  background: $color-white;
  @include tab() {
    width: 100vw;
  }
}
</style>
