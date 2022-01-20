<template>
  <div class="login">
    <div class="background-log">
      <div class="background-log__item">
        <div class="background-log__shadow-rose-top" />
      </div>
      <div class="background-log__item">
        <div class="background-log__shadow-rose-bot" />
      </div>
      <div class="background-log__item">
        <div class="background-log__shadow-blue" />
      </div>
      <div class="background-log__item" v-for="(i, k) in new Array(3)" :key="k">
        <div
          class="background-log__box-rose"
          :class="`background-log__box-rose--${k + 1}`"
        />
      </div>
      <div class="background-log__item" v-for="(i, k) in new Array(3)" :key="k">
        <div
          class="background-log__box-blue"
          :class="`background-log__box-blue--${k + 1}`"
        />
      </div>
    </div>
    <h1 class="heading heading--h1 heading--grad3 login__title">
      Bounty Hunt & Airdrop
    </h1>
    <LoginForm />
    <div class="social">
      <p class="social__text">or</p>
      <div class="social__line"></div>
      <p class="social__text">Enter from social:</p>
      <div class="social__icons">
        <img src="icon/google.svg" alt="" />
        <img src="icon/telegram.svg" alt="" />
        <img src="icon/facebook.svg" alt="" />
        <img src="icon/linkedin.svg" alt="" />
      </div>
    </div>
  </div>
</template>

<script>
import LoginForm from "../components/login-form";

export default {
  name: "Login",
  components: { LoginForm },
};
</script>

<style lang="scss">
.login {
  position: relative;
  //overflow-x: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  padding: 140px 10px 70px;
  gap: 24px;

  &__title {
    margin-bottom: 45px;
    height: 50px;
    font-size: 49px;
    z-index: 2;
    @include mob() {
      margin-bottom: 10px;
      height: 100px;
      text-align: center;
      color: $color-accent;
      background: gradient-accent(360deg, 35%, 71%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }
  }

  @include mob() {
  }
}

.social {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 10px;
  z-index: 2;

  &__text {
    font-family: adineuePROCyr, serif;
    font-size: 16px;
    font-style: normal;
    font-weight: bold;
    line-height: 200%;
    color: $color-white;
  }

  &__line {
    background: radial-gradient(#64e2ff 0%, rgba(100, 226, 255, 0) 100%);
    width: 580px;
    height: 1px;
    @include tab() {
      width: 150%;
    }
    @include mob() {
      width: 100%;
    }
  }

  &__icons {
    display: flex;
    gap: 30px;
    padding-top: 20px;

    img {
      cursor: pointer;
    }
  }
}

.background-log {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  background: linear-gradient(
    110deg,
    rgba(228, 14, 207, 0.01) 35%,
    rgba(33, 212, 253, 0.01) 65%
  );
  overflow: hidden;

  &__item {
    position: absolute;
    width: 100%;
    height: 100%;
  }

  &__shadow-rose-top {
    position: absolute;
    background-color: $color-accent;
    opacity: 0.15;
    border-radius: 50%;
    filter: blur(640px);

    width: 1300px;
    height: 1300px;
    top: -45%;
    left: -35%;

    @include lap() {
      left: -45%;
      top: -60%;
    }
    @include mob() {
      width: 700px;
      height: 700px;
      top: -10%;
      left: -70%;
    }
  }

  &__shadow-rose-bot {
    position: absolute;
    background-color: $color-accent;
    opacity: 0.1;
    border-radius: 50%;
    filter: blur(640px);

    width: 900px;
    height: 900px;
    bottom: -20%;
    left: -30%;
    @include lap() {
      left: -40%;
    }
    //@include tab() {
    //  left: -90%;
    //  top: 70%;
    //}
    //@include mob() {
    //  width: 600px;
    //  height: 600px;
    //}
    @include mob() {
      width: 600px;
      height: 600px;
      left: -60%;
    }
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
    @include lap() {
      left: 60%;
    }
    @include mob() {
      width: 500px;
    }
  }

  &__box-rose {
    position: absolute;
    background-image: url("../image/box-rose.png");
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;

    &--1 {
      width: 83px;
      height: 74px;
      top: 72%;
      left: 2%;
      transform: rotate(45deg);

      @include lap() {
        top: 85%;
        left: 10%;
      }
      @include tab() {
        top: 90%;
        left: 6%;
      }
      @include mob() {
        width: 51px;
        height: 45px;
        top: 8%;
        left: 80%;
      }
    }

    &--2 {
      width: 261px;
      height: 233px;
      top: 40%;
      left: 5%;
      transform: rotate(-16deg);

      @include lap() {
        top: 50%;
        left: -5%;
      }
      @include tab() {
        width: 200px;
        height: 180px;
        top: 60%;
      }
      @include mob() {
        display: none;
      }
    }

    &--3 {
      width: 414px;
      height: 370px;
      top: 5%;
      left: -10%;
      transform: matrix(-0.94, -0.34, -0.34, 0.94, 0, 0);
      filter: blur(15px);

      @include lap() {
        top: -5%;
        left: -5%;
      }
      @include tab() {
        width: 316px;
        height: 280px;
        top: -5%;
        left: -10%;
      }
      @include mob() {
        width: 200px;
        height: 180px;
        filter: blur(7px);
      }
    }
  }

  &__box-blue {
    position: absolute;
    background-image: url("../image/box-blue.png");
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;

    &--1 {
      width: 108px;
      height: 96px;
      top: 10%;
      right: 17%;
      transform: rotate(-15deg);

      @include lap() {
        top: 20%;
        right: 15%;
      }
      @include tab() {
        top: 10%;
        right: 5%;
      }
      @include mob() {
        width: 53px;
        height: 47px;
        top: 30%;
      }
    }

    &--2 {
      width: 316px;
      height: 280px;
      top: 47%;
      right: 8%;
      transform: rotate(67deg);

      @include lap() {
        top: 65%;
        right: -2%;
      }
      @include tab() {
        width: 261px;
        height: 233px;
        top: 78%;
        right: -6%;
      }
      @include mob() {
        display: none;
      }
    }

    &--3 {
      width: 508px;
      height: 451px;
      top: 8%;
      right: -17%;
      transform: rotate(-20deg);
      filter: blur(15px);

      @include lap() {
        top: 10%;
        right: -22%;
      }
      @include tab() {
        width: 414px;
        height: 370px;
        top: 25%;
        right: -35%;
      }
      @include mob() {
        width: 140px;
        height: 124px;
        filter: blur(5px);
        opacity: 0.5;
        left: -10%;
      }
    }
  }
}
</style>
