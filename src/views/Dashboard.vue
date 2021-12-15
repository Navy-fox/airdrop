<template>
  <div class="dashboard">
    <div class="wrapper grid">
      <h1 class="dashboard__heading">
        <span class="heading heading--grad2"> User Dashboard </span>
      </h1>
      <Balance class="balance" />
      <Information class="information" />
      <ChartTokens class="chart-tokens" />
      <Transactions class="history" />
      <AirdropHistory class="airdrop-history" />
    </div>
    <Follow class="follow" />
    <div class="background-dash">
      <div class="background-dash__item">
        <div class="background-dash__shadow-rose-top" />
      </div>
      <div class="background-dash__item">
        <div class="background-dash__shadow-rose-bot" />
      </div>
      <div class="background-dash__item">
        <div class="background-dash__shadow-blue" />
      </div>
      <div class="background-dash__item">
        <div class="background-dash__box-rose" />
      </div>
      <div class="background-dash__item">
        <div class="background-dash__box-blue" />
      </div>
      <div class="background-dash__item">
        <div class="background-dash__shadow-bottom" />
      </div>
    </div>
  </div>
</template>

<script>
import Balance from "../components/dashboard-components/balance";
import Information from "../components/dashboard-components/information";
import ChartTokens from "../components/dashboard-components/chart-tokens";
import AirdropHistory from "../components/dashboard-components/airdrop-history";
import Transactions from "../components/dashboard-components/transactions";
import Follow from "../components/dashboard-components/follow";

export default {
  name: "Dashboard",
  components: {
    Follow,
    Transactions,
    AirdropHistory,
    ChartTokens,
    Information,
    Balance,
  },
};
</script>

<style lang="scss">
.dashboard {
  background: linear-gradient(
    110deg,
    rgba(228, 14, 207, 0.01) 35%,
    rgba(33, 212, 253, 0.01) 65%
  );
  overflow: hidden;
  position: relative;

  &__heading {
    grid-column: span 12;
    padding-top: 110px;

    .heading {
      font-size: 48px;
      line-height: 159%;
    }
  }
}

.background-dash {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;

  &__item {
    position: absolute;
    width: 100%;
    height: 100%;
  }

  &__shadow-rose-top {
    position: absolute;
    background-color: $color-accent;
    opacity: 0.2;
    border-radius: 50%;
    filter: blur(640px);

    width: 1300px;
    height: 1300px;
    top: -45%;
    left: -35%;

    //@include lap() {
    //  display: none;
    //}
    //@include mob() {
    //  display: block;
    //  width: 350px;
    //  height: 350px;
    //  top: 4%;
    //  left: 0;
    //}
  }

  &__shadow-rose-bot {
    position: absolute;
    background-color: $color-accent;
    opacity: 0.15;
    border-radius: 50%;
    filter: blur(640px);

    width: 900px;
    height: 900px;
    top: 15%;
    left: -30%;
    //@include lap() {
    //  left: -80%;
    //}
    //@include tab() {
    //  left: -90%;
    //  top: 70%;
    //}
    //@include mob() {
    //  width: 600px;
    //  height: 600px;
    //}
  }

  &__shadow-blue {
    position: absolute;
    background-color: $color-primary;
    opacity: 0.1;
    border-radius: 50%;
    filter: blur(640px);

    width: 1000px;
    height: 100vh;
    top: 0;
    left: 70%;
  }

  &__box-rose {
    position: absolute;
    background-image: url("/image/box-rose.png");
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;

    width: 414px;
    height: 370px;
    top: 30%;
    left: -10%;
    transform: matrix(-0.94, -0.34, -0.34, 0.94, 0, 0);
    filter: blur(15px);
    animation: box-r 12s 5s infinite alternate
      cubic-bezier(0.455, 0.03, 0.515, 0.955);

    @keyframes box-r {
      0% {
        transform: rotateZ(0deg) translate3d(20%, 20%, 20px) rotateZ(0deg);
      }
      100% {
        transform: rotateZ(-180deg) translate3d(0, 20%, 20px) rotateZ(180deg);
      }
    }

    @include tab() {
      animation: none;
    }

    //@include lap() {
    //  display: none;
    //}
  }

  &__box-blue {
    position: absolute;
    background-image: url("/image/box-blue.png");
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;

    width: 508px;
    height: 451px;
    top: 8%;
    right: -17%;
    transform: rotate(-10deg);
    filter: blur(15px);

    animation: box-b 25s 5s infinite alternate
      cubic-bezier(0.455, 0.03, 0.515, 0.955);

    @keyframes box-b {
      0% {
        transform: rotateZ(0deg) translate3d(20%, 20%, 20px) rotateZ(0deg);
      }
      100% {
        transform: rotateZ(180deg) translate3d(0, 10%, 20px) rotateZ(-180deg);
      }
    }

    @include tab() {
      animation: none;
    }
    //@include lap() {
    //  display: none;
    //}
  }

  &__shadow-bottom {
    position: absolute;
    background-color: $color-primary;
    opacity: 0.4;
    border-radius: 50%;
    filter: blur(640px);

    width: 100vw;
    height: 500px;
    top: 100%;
  }
}

.balance,
.information,
.chart-tokens {
  grid-column: span 4;
  z-index: 2;
}

.history,
.airdrop-history {
  grid-column: span 6;
  z-index: 2;
}

.follow {
  grid-column: span 12;
  //z-index: 2;
}
</style>
