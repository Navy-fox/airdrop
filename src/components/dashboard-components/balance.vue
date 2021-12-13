<template>
  <DashboardBlock title="Balance">
    <div class="balance-main">
      <img src="icon/logo-circle.svg" alt="" class="balance-main__img" />
      <span class="heading heading--h2 heading--grad-revert">0.22045</span>
      <p class="heading heading--desc">FOIL</p>
    </div>
    <div class="line"></div>
    <div class="wallet">
      <p class="wallet__title">FOIL Wallet:</p>
      <input class="wallet__input" />
      <button class="wallet__btn button button--gradient">Withdraw</button>
    </div>
  </DashboardBlock>
</template>

<script>
import DashboardBlock from "./dashboard-block";

export default {
  name: "balance",
  components: { DashboardBlock },
};
</script>

<style lang="scss">
.balance-main {
  display: flex;
  align-items: baseline;
  justify-content: start;
  gap: 10px;
  padding: 25px 24px;

  &__img {
    width: 37px;
    height: 37px;
  }

  .heading {
    line-height: 100%;
  }
}

.heading--desc {
  font-size: 12px;
}

.line {
  width: 100%;
  height: 1px;
  background: #272c3c;
}

.wallet {
  padding: 25px 24px;
  display: flex;
  flex-direction: column;
  gap: 15px;
  &__title {
    font-family: LabGrotesque, serif;
    font-size: 16px;
    font-style: normal;
    font-weight: 400;
    color: $color-white;
  }

  &__input {
    background: #0c111d;
    border-radius: 6px;
    font-family: LabGrotesque, serif;
    font-size: 16px;
    color: #2c3243;
    border: #2c3243 solid 1px;
    padding: 8px 15px;
    width: 100%;

    &:focus {
      border: $color-primary solid 1px;
      color: $color-white;
    }
  }

  &__btn {
    width: 140px;
    height: 45px;
    padding: 0;
    font-size: 15px;
    margin-top: 25px;
  }
}
</style>
