<template>
  <div class="main">
    <div class="parallax">
      <div class="body">
        <div class="container wrapper grid">
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
              :style="transform.shadow"
              class="parallax-img__shadow-rose parallax-img__shadow-rose--1"
            ></div>
          </div>
          <div class="parallax-img__item">
            <div
              :style="transform.shadow"
              class="parallax-img__shadow-blue parallax-img__shadow-blue--1"
            ></div>
          </div>
          <div class="parallax-img__item">
            <div :style="transform.sky" class="parallax-img__sky"></div>
          </div>
          <div class="parallax-img__item">
            <div
              :style="transform.shadow"
              class="parallax-img__shadow-rose parallax-img__shadow-rose--2"
            ></div>
          </div>
          <div class="parallax-img__item">
            <div
              :style="transform.shadow"
              class="parallax-img__shadow-blue parallax-img__shadow-blue--2"
            ></div>
          </div>
          <div :style="transform.boxLV1" class="parallax-img__item">
            <div class="parallax-img__box-rose parallax-img__box-rose--0"></div>
          </div>
          <div
            :style="transform[`boxLV${k + 1}`]"
            class="parallax-img__item"
            v-for="(i, k) in new Array(4)"
            :key="`${k}-b`"
          >
            <div
              :class="`parallax-img__box-blue--${k + 1}`"
              class="parallax-img__box-blue"
            ></div>
          </div>
          <div class="parallax-img__item">
            <div :style="transform.human" class="parallax-img__human"></div>
          </div>
          <div
            :style="transform.boxOpen"
            style="mix-blend-mode: screen"
            class="parallax-img__item"
          >
            <div class="parallax-img__box-open"></div>
          </div>
          <div
            :style="transform[`boxLV${k + 1}`]"
            class="parallax-img__item"
            v-for="(i, k) in new Array(5)"
            :key="k"
          >
            <div
              :class="`parallax-img__box-rose--${k + 1}`"
              class="parallax-img__box-rose"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "main",
  data() {
    return {
      // коэффициенты
      forShadow: -30,
      forSky: 40,
      forBoxLV5: -25,
      forBoxLV4: 20,
      forBoxLV3: -20,
      forBoxLV2: -15,
      forBoxLV1: 15,
      forHuman: 20,
      forBoxOpen: 10,
      //скорость анимации
      speed: 0.05,
      // текущее положение элемента
      positionX: 0,
      positionY: 0,
      // положение элемента в процентах
      coordXprocent: 0,
      coordYprocent: 0,
      parallax: null,
      transform: {
        sky: "",
        human: "",
        boxLV1: "",
        boxLV2: "",
        boxLV3: "",
        boxLV4: "",
        boxLV5: "",
        boxOpen: "",
        shadow: "",
      },
    };
  },
  methods: {
    setMouseParallaxStyle() {
      this.parallax = this.$el.querySelector(".parallax");
      if (this.parallax) {
        const distX = this.coordXprocent - this.positionX;
        const distY = this.coordYprocent - this.positionY;

        this.positionX = this.positionX + distX * this.speed;
        this.positionY = this.positionY + distY * this.speed;

        this.transform.boxOpen = `transform: translate(${
          this.positionX / this.forBoxOpen
        }%,${this.positionY / this.forBoxOpen}%)`;
        this.transform.boxLV1 = `transform: translate(${
          this.positionX / this.forBoxLV1
        }%,${this.positionY / this.forBoxLV1}%)`;
        this.transform.human = `transform: translate(${
          this.positionX / this.forHuman
        }%,${this.positionY / this.forHuman}%)`;
        this.transform.boxLV2 = `transform: translate(${
          this.positionX / this.forBoxLV2
        }%,${this.positionY / this.forBoxLV2}%)`;
        this.transform.boxLV3 = `transform: translate(${
          this.positionX / this.forBoxLV3
        }%,${this.positionY / this.forBoxLV3}%)`;
        this.transform.boxLV4 = `transform: translate(${
          this.positionX / this.forBoxLV4
        }%,${this.positionY / this.forBoxLV4}%)`;
        this.transform.boxLV5 = `transform: translate(${
          this.positionX / this.forBoxLV5
        }%,${this.positionY / this.forBoxLV5}%)`;
        this.transform.shadow = `transform: translate(${
          this.positionX / this.forShadow
        }%,${this.positionY / this.forShadow}%)`;
        this.transform.sky = `transform: translate(${
          this.positionX / this.forSky
        }%,${this.positionY / this.forSky}%)`;

        requestAnimationFrame(this.setMouseParallaxStyle);

        this.parallax.addEventListener("mousemove", this.forEventListener);
      }
    },

    async forEventListener(e) {
      // получение шырины и высоты блока
      const parallaxWidth = this.parallax.offsetWidth;
      const parallaxHeight = this.parallax.offsetHeight;
      // начальное положение когда курсор в центре
      const coordX = e.pageX - parallaxWidth / 2;
      const coordY = e.pageY - parallaxHeight / 2;
      //получение процентных значений
      this.coordXprocent = (coordX / parallaxWidth) * 100;
      this.coordYprocent = (coordY / parallaxHeight) * 100;
    },
  },

  mounted() {
    this.setMouseParallaxStyle();
  },
  beforeDestroy() {
    this.parallax.removeEventListener("mousemove", this.forEventListener());
  },
};
</script>

<style lang="scss">
.main {
  min-height: 100vh;
  @include tab() {
    max-height: 840px;
  }
}

.container {
  padding-top: 5%;
  @include lap() {
    padding-top: 8%;
  }
  @include mob() {
    padding-top: 30%;
  }
}

.body {
  position: fixed;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;

  &__title {
    display: flex;
    flex-direction: column;
    grid-column: 1/6;
    gap: 10px;
    z-index: 2;
  }

  &__text {
    font-family: adineuePROCyr, serif;
    font-size: 36px;
    line-height: 134%;
    font-style: normal;
    font-weight: bold;
    color: $color-white;
    grid-column: 1/8;
    padding-top: 5%;
    z-index: 2;
    @include lap() {
      padding-top: 0;
      padding-bottom: 5%;
    }

    @include tab() {
      font-size: 28px;
    }
    @include mob() {
      display: none;
    }
  }
}

.parallax {
  min-height: 100vh;

  &:after {
    content: "";
    position: absolute;
    bottom: 0;
    width: 100%;
    height: 200px;
    background: linear-gradient(rgba(10, 9, 20, 0) 0%, $color-dark 100%);
  }
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
    background-image: url("../image/sky.png");
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
    background-image: url("../image/human.png");
    background-position: top;
    background-repeat: no-repeat;
    background-size: cover;

    @include tab() {
      background-position: top left 61%;
    }
  }

  &__box-open {
    position: absolute;
    width: 262px;
    height: 229px;
    top: 51%;
    left: 45%;
    transform: rotate(11deg);
    //mix-blend-mode: screen;
    background-image: url("../image/box-open.png");
    background-position: center;
    background-repeat: no-repeat;
    background-size: auto auto;

    @include lap() {
      top: 45%;
      left: 43%;
    }
    @include tab() {
      left: 30%;
    }
    @include mob() {
      width: 152px;
      height: 133px;
      background-size: contain;
      top: 47%;
      left: 25%;
    }
  }

  &__box-rose {
    position: absolute;
    background-image: url("../image/box-rose.png");
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;

    &--0 {
      width: 78px;
      height: 70px;
      top: 56%;
      left: 35.5%;
      transform: rotate(-60deg);
      @include lap() {
        top: 54%;
        left: 34%;
      }
      @include tab() {
        top: 52%;
        left: 15%;
      }
      @include mob() {
        width: 31px;
        height: 28px;
        //top: 52%;
        //left: 15%;
      }
    }

    &--1 {
      width: 414px;
      height: 370px;
      top: 10%;
      left: -2%;
      transform: matrix(-0.94, -0.34, -0.34, 0.94, 0, 0);
      filter: blur(15px);

      @include lap() {
        display: none;
      }
      @include tab() {
        display: block;
        filter: none;
        width: 56px;
        height: 50px;
        top: 20%;
        left: 6%;
      }
    }

    &--2 {
      width: 80px;
      height: 70px;
      top: 50%;
      left: 9%;
      transform: rotate(45deg);

      @include lap() {
        display: none;
      }
    }

    &--3 {
      width: 196px;
      height: 175px;
      top: 80%;
      left: 5%;
      transform: rotate(81deg);
      @include lap() {
        display: none;
      }
    }

    &--4 {
      width: 196px;
      height: 175px;
      top: 25%;
      left: 47%;
      @include lap() {
        left: 45%;
      }
      @include tab() {
        display: none;
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
      width: 508px;
      height: 451px;
      top: 17%;
      left: 82%;
      transform: rotate(-9deg);
      filter: blur(12px);
      @include lap() {
        display: none;
      }
    }

    &--2 {
      width: 108px;
      height: 96px;
      top: 21%;
      left: 73%;
      transform: rotate(-15deg);
      @include lap() {
        left: 77%;
      }
      @include tab() {
        left: 80%;
      }
    }

    &--3 {
      width: 316px;
      height: 281px;
      top: 60%;
      left: 80%;
      transform: rotate(86deg);
      @include lap() {
        display: none;
      }
    }

    &--4 {
      width: 110px;
      height: 98px;
      top: 54%;
      left: 16.5%;
      transform: rotate(-55deg);
      @include lap() {
        top: 50%;
        left: 7%;
      }
      @include tab() {
        display: none;
      }
    }
  }

  &__shadow-rose {
    position: absolute;
    background-color: $color-accent;
    opacity: 0.4;
    border-radius: 50%;
    filter: blur(640px);

    &--1 {
      width: 800px;
      height: 800px;
      top: 60%;
      left: -20%;
      @include tab() {
        left: -60%;
        top: 40%;
      }
    }

    &--2 {
      width: 1200px;
      height: 1200px;
      top: -20%;
      left: -20%;
      @include tab() {
        left: -60%;
        top: -50%;
      }
    }
  }

  &__shadow-blue {
    position: absolute;
    background-color: $color-primary;
    opacity: 0.4;
    border-radius: 50%;
    filter: blur(640px);

    &--1 {
      width: 750px;
      height: 750px;
      top: 55%;
      left: 53%;
      @include tab() {
        left: 40%;
        top: 40%;
      }
    }

    &--2 {
      width: 650px;
      height: 650px;
      top: 20%;
      left: 70%;
      @include tab() {
        top: 15%;
      }
    }
  }
}

.button {
  width: 250px;
  height: 70px;
  grid-column: 1/5;
  @include mob() {
    display: flex;
    width: 100%;
    align-items: center;
    justify-content: center;
    height: 60px;
    margin-top: auto;
    margin-bottom: 15px;
    grid-column: span 8;
  }
}
</style>
