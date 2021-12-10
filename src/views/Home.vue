<template>
  <div class="home">
<!--    <ModalSettings />-->
<!--    <ModalSupport />-->
    <ModalSuccess />
    <Main />
    <section class="content-wrapper">
      <div class="background">
        <div class="background__item">
          <div class="background__bg-to-logo" />
        </div>
        <div class="background__item">
          <div class="background__bg-to-logo-2" />
        </div>
        <div class="background__item">
          <div class="background__shadow-rose-top" />
        </div>
        <div class="background__item">
          <div class="background__shadow-blue-top" />
        </div>
        <div class="background__item">
          <div class="background__shadow-rose-bot" />
        </div>
        <div class="background__item">
          <div class="background__shadow-blue-bot" />
        </div>
        <div class="background__item">
          <div class="background__shadow-bottom" />
        </div>
        <div class="background__item">
          <div class="background__box-rose" />
        </div>
        <div class="background__item">
          <div class="background__box-blue" />
        </div>
      </div>
      <div class="content">
        <Actual />
        <Completed />
        <Subscribe />
      </div>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src

import Main from "../components/main";
import Actual from "../components/actual";
import Completed from "../components/completed";
import Subscribe from "../components/subscribe";
import ModalSuccess from "../components/modal/modal-success";

export default {
  name: "Home",
  components: {
    ModalSuccess,
    Subscribe,
    Completed,
    Actual,
    Main,
  },
};
</script>

<style lang="scss">
.content-wrapper {
  position: relative;
  background: #0a0914;
  z-index: 2;
  overflow: hidden;
}

.content {
  position: sticky;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
}

.background {
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

  &__bg-to-logo {
    position: absolute;
    background-image: url("/image/bg-to-logo.png");
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    width: 690px;
    height: 470px;
    opacity: 0.3;
    filter: blur(15px);
    left: 10%;
    top: 2%;
    @include lap() {
      left: 0;
    }
    @include tab() {
      left: 10%;
    }
    @include mob() {
      left: -10%;
      top: 0;
      transform: rotate(-20deg);
    }
  }

  &__bg-to-logo-2 {
    position: absolute;
    background-image: url("/image/bg-to-logo.png");
    background-position: center;
    background-repeat: no-repeat;
    background-size: contain;
    width: 450px;
    height: 450px;
    transform: rotate(-20deg);
    left: 22%;
    top: 2%;
    @include lap() {
      left: 8%;
    }
    @include tab() {
      left: 22%;
    }
    @include mob() {
      left: 0;
    }
  }

  &__box-rose {
    position: absolute;
    background-image: url("/image/box-rose.png");
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;

    width: 295px;
    height: 260px;
    top: 70%;
    left: -4%;
    transform: rotate(-20deg);
    animation: box-r 12s 5s infinite alternate
      cubic-bezier(0.455, 0.03, 0.515, 0.955);

    @keyframes box-r {
      0% {
        transform: rotateZ(0deg) translate3d(20%, 40%, 20px) rotateZ(0deg);
      }
      100% {
        transform: rotateZ(-180deg) translate3d(0, 50%, 20px) rotateZ(180deg);
      }
    }

    @include tab() {
      animation: none;
    }
    @include mob() {
    }
  }

  &__box-blue {
    position: absolute;
    background-image: url("/image/box-blue.png");
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;

    width: 560px;
    height: 500px;
    top: 70%;
    left: 82%;
    transform: rotate(-9deg);
    filter: blur(12px);
    animation: box-b 8s 8s infinite alternate
      cubic-bezier(0.455, 0.03, 0.515, 0.955);

    @keyframes box-b {
      0% {
        transform: rotateZ(0deg) translate3d(0, 5%, 0) rotateZ(0deg);
      }
      100% {
        transform: rotateZ(360deg) translate3d(0, 20%, 0) rotateZ(-360deg);
      }
    }

    @include tab() {
      animation: none;
    }
    @include mob() {
    }
  }

  &__shadow-rose-top {
    position: absolute;
    background-color: $color-accent;
    opacity: 0.3;
    border-radius: 50%;
    filter: blur(640px);

    width: 900px;
    height: 900px;
    top: 2%;
    left: -40%;

    @include lap() {
      display: none;
    }
    @include mob() {
      display: block;
      width: 350px;
      height: 350px;
      top: 4%;
      left: 0;
    }
  }

  &__shadow-rose-bot {
    position: absolute;
    background-color: $color-accent;
    opacity: 0.3;
    border-radius: 50%;
    filter: blur(640px);

    width: 1300px;
    height: 1300px;
    top: 50%;
    left: -50%;
    @include lap() {
      left: -80%;
    }
    @include tab() {
      left: -90%;
      top: 70%;
    }
    @include mob() {
      width: 600px;
      height: 600px;
    }
  }

  &__shadow-blue-top {
    position: absolute;
    background-color: $color-primary;
    opacity: 0.3;
    border-radius: 50%;
    filter: blur(640px);

    width: 1200px;
    height: 200px;
    top: 5%;
    right: -5%;

    @include lap() {
      display: none;
    }
  }

  &__shadow-blue-bot {
    position: absolute;
    background-color: $color-primary;
    opacity: 0.3;
    border-radius: 50%;
    filter: blur(640px);

    width: 1300px;
    height: 1300px;
    top: 40%;
    right: -55%;

    @include lap() {
      right: -80%;
    }
    @include tab() {
      right: -90%;
      top: 45%;
    }
    @include mob() {
      width: 600px;
      height: 600px;
    }
  }

  &__shadow-bottom {
    position: absolute;
    background-color: $color-primary;
    opacity: 0.4;
    border-radius: 50%;
    filter: blur(640px);

    width: 100vw;
    height: 1000px;
    top: 100%;
  }
}
</style>
