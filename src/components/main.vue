<template>
  <div class="wrapper grid main">
    <h1 class="title-main">
      <span class="heading heading--h1"> Foil.Network </span>
      <span class="heading heading--h1 heading--grad1">
        Bounty Hunt & Airdrop
      </span>
    </h1>
    <button class="button button--gradient">Actual Airdrops</button>
    <p class="text-main">
      Earn FOIL by participating in the bounty campaign. The Blockchain
      Interactions crypto rewards event brings the important mission of
      scalability and sustainability of the FOIL elastic blockchain.
    </p>
  </div>
</template>

<script>
export default {
  name: "main",
};
</script>

<style lang="scss">
.main {
  padding-top: 130px;
}
.title-main {
  display: flex;
  flex-direction: column;
  grid-column: 1/7;
  //padding-bottom: 10px;
  gap: 10px;
}
.button {
  width: 250px;
  grid-column: 1/5;
  margin-bottom: 50px;
}
.text-main {
  font-family: adineuePROCyr, serif;
  font-size: 41px;
  line-height: 134%;
  font-style: normal;
  font-weight: bold;
  color: $color-white;
  grid-column: 1/8;
}
</style>
