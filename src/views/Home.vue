<template>
  <div class="home">
    <p class="test">Astolfo</p>
    <div class="test-buttons">
      <button class="test-button test-button__f">fuck</button>
      <div class="suck">
        <button class="test-button test-button__s">suck</button>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",
  components: {},
};
</script>

<style lang="scss">
.test {
  font-family: adineuePROCyr, serif;
  font-size: 72px;
  letter-spacing: 30px;
  padding-top: 150px;
  text-align: center;
  text-transform: uppercase;
  color: $color-gradient-accent;

  background: gradient-accent(265deg, 21%, 66%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.test-buttons {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 30px;
}

.test-button {
  font-family: adineuePROCyr, serif;
  font-size: 36px;
  letter-spacing: 10px;
  color: $color-white;
  text-transform: uppercase;

  cursor: pointer;

  &__f {
    background: gradient-accent(-60deg, 21%, 66%);
    border: none;
    border-radius: 15px;
    padding: 10px;

    &:hover {
      //transition: 1s;
      //box-shadow: 10px 10px 10px rgba(7, 196, 239, 0.4);
      transform: scale(1.05);
    }
  }

  &__s {
    color: #e40ecf;
    background: gradient-accent(265deg, 21%, 66%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;

    border: none;
  }
}

.suck {
  --b: 5px; /* border width*/
  --r: 15px; /* the radius */

  padding: calc(var(--b) + 5px);
  z-index: 0;

  color: #e40ecf;
  display: inline-block;
  //margin: 10px;
  //width: 39px;
  //height: 39px;
  position: relative;

  &:before {
    content: "";
    position: absolute;
    z-index: -1;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    padding: var(--b);
    border-radius: var(--r);
    //-webkit-mask: -webkit-gradient(
    //      linear,
    //      left top,
    //      right bottom,
    //      color-stop(1, rgba(0, 0, 0, 1))
    //    ) content-box,
    //  -webkit-gradient(linear, left top, right bottom, color-stop(1, rgba(0, 0, 0, 1)));
    -webkit-mask: linear-gradient(#fff 0 0) content-box,
      linear-gradient(#fff 0 0);
    -webkit-mask-composite: destination-out;
    mask-composite: exclude;
    background: linear-gradient(-135deg, #21d4fd 22%, #e40ecf 70%);
  }

  &:hover {
    //transition: 1s;
    //box-shadow: 10px 10px 10px rgba(7, 196, 239, 0.4);
    transform: scale(1.05);
  }
}
</style>
