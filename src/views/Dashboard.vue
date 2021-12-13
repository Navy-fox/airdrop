<template>
  <div class="dashboard wrapper grid">
    <h1 class="dashboard__heading">
      <span class="heading heading--grad2"> User Dashboard </span>
    </h1>
    <Balance class="balance" />
    <Information class="information" />
    <ChartTokens class="chart-tokens" />
    <Transactions class="transactions" />
    <AirdropHistory class="airdrop-history" />
  </div>
</template>

<script>
import Balance from "../components/dashboard-components/balance";
import Information from "../components/dashboard-components/information";
import ChartTokens from "../components/dashboard-components/chart-tokens";
import AirdropHistory from "../components/dashboard-components/airdrop-history";
import Transactions from "../components/dashboard-components/transactions";

export default {
  name: "Dashboard",
  components: { Transactions, AirdropHistory, ChartTokens, Information, Balance },
};
</script>

<style lang="scss">
.dashboard {
  &__heading {
    grid-column: span 12;
    padding-top: 110px;

    .heading {
      font-size: 48px;
      line-height: 159%;
    }
  }
}

.balance,
.information,
.chart-tokens {
  grid-column: span 4;
}

.transactions,
.airdrop-history {
  grid-column: span 6;
}
</style>
