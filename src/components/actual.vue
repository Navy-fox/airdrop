<template>
  <div class="wrapper grid actual">
    <div class="logo-circle">
      <img src="icon/logo-circle.svg" alt="" class="icon" />
    </div>
    <div class="info">
      <p class="info__text">
        Test the FOIL NFT storage, send and receive encrypted messages,
        transactions and save NFT content over blockchain and bring the crypto
        benchmark tests of FOIL Network live! 1,250,000 FOIL are reserved for
        the crypto airdrop and bounty participants.
      </p>
      <h2 class="info__title">
        <span class="heading heading--h2">
          Join FOIL Blockchain Interactions and earn FOIL crypto.
        </span>
      </h2>
      <button class="info__but"></button>
    </div>
    <div class="card"></div>
  </div>
</template>

<script>
export default {
  name: "actual",
};
</script>

<style lang="scss">
.logo-circle {
  grid-column: span 6;
}

.info {
  grid-column: span 6;
}
</style>
