<template>
  <DashboardBlock title="Information" class="information">
    <div class="information-image"></div>
    <div class="information-info">
      <span class="information-info__title heading heading--h3 heading--grad2">
        Actuail Airdrop titile
      </span>
      <p class="information-info__text">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
        tempor incididunt ut labore et dolore magna aliqua.
      </p>
      <button class="information-info__arrow">
        <Arrow class="information-info__img-arrow" />
      </button>
    </div>
  </DashboardBlock>
</template>

<script>
import DashboardBlock from "./dashboard-block";
import Arrow from "../icon/arrow";

export default {
  name: "information",
  components: { Arrow, DashboardBlock },
};
</script>

<style lang="scss">
.information {
  position: relative;
  overflow: hidden;
}

.information-image {
  width: 100%;
  height: 311px;
  background-image: url(/image/card-actual/c2.png);
  background-size: cover;
  background-position: center center;
  background-repeat: no-repeat;
  position: center;
}

.information-info {
  position: absolute;
  width: 100%;
  background: rgba(60, 60, 100, 0.9);
  left: 0;
  bottom: -70px;

  padding: 14px 24px;

  display: grid;
  grid-template-columns: 1fr 48px;
  column-gap: 20px;
  row-gap: 10px;
  align-items: center;
  cursor: pointer;
  transition: all ease-in-out 0.5s;

  &:hover {
    bottom: 0;
    transition: all ease-in-out 0.8s;
  }

  &__title {
    grid-column: span 2;
  }
  &__text {
    grid-column: 1/2;
    font-family: LabGrotesque, serif;
    font-style: normal;
    font-weight: 400;
    font-size: 13px;
    color: $color-white;
  }
  &__arrow {
    display: flex;
    align-items: center;
    justify-content: center;

    grid-column: 2/3;
    width: 48px;
    height: 48px;
    border-radius: 50%;
    background: none;
    border: 2px solid rgba(255, 255, 255, 0.4);
    cursor: pointer;
  }
  &__img-arrow {
    height: 8px;
    width: 14px;
  }
}
</style>
