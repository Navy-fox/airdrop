<template>
  <div class="main">
    <div class="parallax">
      <div class="wrapper grid body">
        <h1 class="body__title">
          <span class="heading heading--h1"> Foil.Network </span>
          <span class="heading heading--h1 heading--grad1">
            Bounty Hunt & Airdrop
          </span>
        </h1>
        <button class="button button--gradient">Actual Airdrops</button>
        <p class="body__text">
          Earn FOIL by participating in the bounty campaign. The Blockchain
          Interactions crypto rewards event brings the important mission of
          scalability and sustainability of the FOIL elastic blockchain.
        </p>
      </div>
      <div class="parallax-img">
        <div class="parallax-img__item">
          <div
            class="parallax-img__shadow-rose parallax-img__shadow-rose--1"
          ></div>
        </div>
        <div class="parallax-img__item">
          <div
            class="parallax-img__shadow-blue parallax-img__shadow-blue--1"
          ></div>
        </div>
        <div class="parallax-img__item">
          <div class="parallax-img__sky"></div>
        </div>
        <div class="parallax-img__item">
          <div
            class="parallax-img__shadow-rose parallax-img__shadow-rose--2"
          ></div>
        </div>
        <div class="parallax-img__item">
          <div
            class="parallax-img__shadow-blue parallax-img__shadow-blue--2"
          ></div>
        </div>
        <div class="parallax-img__item">
          <div class="parallax-img__box-rose parallax-img__box-rose--0"></div>
        </div>
        <div class="parallax-img__item" v-for="(i, k) in new Array(4)" :key="k">
          <div
            :class="`parallax-img__box-blue--${k + 1}`"
            class="parallax-img__box-blue"
          ></div>
        </div>
        <div class="parallax-img__item">
          <div class="parallax-img__human"></div>
        </div>
        <div class="parallax-img__item">
          <div class="parallax-img__box-open"></div>
        </div>
        <div class="parallax-img__item" v-for="(i, k) in new Array(5)" :key="k">
          <div
            :class="`parallax-img__box-rose--${k + 1}`"
            class="parallax-img__box-rose"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "main",
};
</script>

<style lang="scss">
.main {
  min-height: 100vh;
}

.body {
  //padding-top: 130px;
  padding-top: 10%;

  &__title {
    display: flex;
    flex-direction: column;
    grid-column: 1/6;
    //padding-bottom: 10px;
    gap: 10px;
    z-index: 2;
  }

  &__text {
    font-family: adineuePROCyr, serif;
    font-size: 41px;
    line-height: 134%;
    font-style: normal;
    font-weight: bold;
    color: $color-white;
    grid-column: 1/8;
    padding-top: 15%;
    z-index: 2;
  }
}

.parallax {
  position: fixed;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
}

.parallax-img {
  position: absolute;
  width: 120%;
  height: 115%;
  top: -10%;
  left: -8%;
  z-index: 1;

  &__item {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
  }

  &__sky {
    position: absolute;
    width: 100%;
    height: 100%;
    left: 0;
    //background: url("/image/sky.png") top / cover no-repeat;
    background-image: url("/image/sky.png");
    background-position: top;
    background-repeat: no-repeat;
    background-size: cover;
    opacity: 0.7;
    mix-blend-mode: color-dodge;
  }

  &__human {
    position: absolute;
    width: 100%;
    height: 60%;
    left: 0;
    bottom: 0;
    //background: url("/image/human.png") top / cover no-repeat;
    background-image: url("/image/human.png");
    background-position: top;
    background-repeat: no-repeat;
    background-size: cover;
  }

  &__box-open {
    position: absolute;
    width: 262px;
    height: 229px;
    top: 51%;
    //left: 1050px;
    left: 45%;
    transform: rotate(11deg);
    mix-blend-mode: screen;
    //background: url("/image/box-open.png") top / auto auto no-repeat;
    background-image: url("/image/box-open.png");
    background-position: center;
    background-repeat: no-repeat;
    background-size: auto auto;
  }

  &__box-rose {
    position: absolute;
    //background: url("/image/box-rose.png") top / cover no-repeat;
    background-image: url("/image/box-rose.png");
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;

    &--0 {
      width: 78px;
      height: 70px;
      top: 56%;
      //left: 820px;
      left: 35.5%;
      transform: rotate(-60deg);
    }

    &--1 {
      width: 414px;
      height: 370px;
      top: 10%;
      //left: -50px;
      left: -2%;
      transform: matrix(-0.94, -0.34, -0.34, 0.94, 0, 0);
      filter: blur(15px);
    }

    &--2 {
      width: 80px;
      height: 70px;
      top: 50%;
      //left: 200px;
      left: 9%;
      transform: rotate(45deg);
    }

    &--3 {
      width: 196px;
      height: 175px;
      top: 80%;
      //left: 115px;
      left: 5%;
      transform: rotate(81deg);
    }

    &--4 {
      width: 196px;
      height: 175px;
      top: 25%;
      //left: 1075px;
      left: 47%;
    }
  }

  &__box-blue {
    position: absolute;
    //background: url("/image/box-rose.png") top / cover no-repeat;
    background-image: url("/image/box-blue.png");
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;

    &--1 {
      width: 508px;
      height: 451px;
      top: 17%;
      left: 82%;
      transform: rotate(-9deg);
      filter: blur(12px);
    }

    &--2 {
      width: 108px;
      height: 96px;
      top: 21%;
      left: 73%;
      transform: rotate(-15deg);
    }

    &--3 {
      width: 316px;
      height: 281px;
      top: 60%;
      left: 80%;
      transform: rotate(86deg);
    }

    &--4 {
      width: 110px;
      height: 98px;
      top: 54%;
      left: 16.5%;
      transform: rotate(-55deg);
    }
  }

  &__shadow-rose {
    position: absolute;
    background-color: $color-gradient-accent;
    opacity: 0.4;
    border-radius: 50%;
    filter: blur(640px);

    &--1 {
      width: 800px;
      height: 800px;
      top: 60%;
      left: -20%;
    }
    &--2 {
      width: 1200px;
      height: 1200px;
      top: -20%;
      left: -20%;
    }
  }
  &__shadow-blue {
    position: absolute;
    background-color: $color-gradient-primary;
    opacity: 0.4;
    border-radius: 50%;
    filter: blur(640px);

    &--1 {
      width: 750px;
      height: 750px;
      top: 55%;
      left: 53%;
    }
    &--2 {
      width: 650px;
      height: 650px;
      top: 20%;
      left: 70%;
    }
  }
}

.button {
  width: 250px;
  grid-column: 1/5;
  margin-bottom: 50px;
}
</style>
