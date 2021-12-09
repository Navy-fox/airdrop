<template>
  <div class="wrapper">
    <div class="subscribe">
      <h2 class="subscribe__title heading heading--grad2">
        Subscribe to us and stay turned!
      </h2>
      <form class="subscribe__form subscribe-form">
        <input
          type="text"
          placeholder="Enter your e-mail"
          class="subscribe-form__input"
        />
        <button class="subscribe-form__btn button">
          <span>Send information</span>
          <Arrow class="subscribe-form" />
        </button>
      </form>
    </div>
  </div>
</template>

<script>
import Arrow from "./icon/arrow";

export default {
  name: "subscribe",
  components: { Arrow },
};
</script>

<style lang="scss">
.subscribe {
  display: flex;
  flex-direction: column;
  gap: 100px;
  padding: 90px 0;
  @include tab() {
    gap: 30px;
  }
  @include mob() {
    padding: 50px 0;
  }

  &__title {
    min-height: 260px;
    @include tab() {
      min-height: 180px;
    }
    @include mob() {
      min-height: 100px;
    }
  }

  &__form {
    width: 100%;
    padding: 60px;
    border-radius: 8px;
    background: gradient(180deg, 0.4, 0.15);
    @include tab() {
      padding: 30px 15px;
    }
  }
}

.subscribe-form {
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  gap: 20px;

  &__input {
    border-radius: 8px;
    border: $color-primary solid 1px;
    font-family: adineuePROCyr, serif;
    font-size: 16px;
    color: $color-white;
    padding: 18px 30px;
    grid-column: span 4;
  }

  &__btn {
    background: $color-primary;
    border-radius: 8px;
    grid-column: span 2;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 20px;
    //padding: 15px 30px;
  }

  @include tab() {
    display: flex;
    flex-direction: column;
  }
}
</style>
