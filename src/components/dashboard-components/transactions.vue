<template>
  <DashboardBlock title="Transactions" class="transactions">
    <div class="transactions__head">
      <span class="type">Type</span>
      <span>Date</span>
      <span> Amount </span>
    </div>
    <div class="transactions__line"></div>
    <div class="transactions__body">
      <div class="transactions__col-1">
        <div
          class="transactions__col-1 transactions__col-1--item"
          v-for="(i, k) in transactions"
          :key="k"
        >
          {{ i.type }}
        </div>
      </div>
      <div class="transactions__col-2">
        <div v-for="(i, k) in transactions" :key="k">
          {{ i.date }}
        </div>
      </div>
      <div class="transactions__col-3">
        <div
          class="transactions__col-3 transactions__col-3--item"
          v-for="(i, k) in transactions"
          :key="k"
        >
          {{ i.amount }}
        </div>
      </div>
    </div>
  </DashboardBlock>
</template>

<script>
import DashboardBlock from "./dashboard-block";

export default {
  name: "transactions",
  components: { DashboardBlock },
  data() {
    return {
      transactions: [
        { type: "Getting a token", date: "10.06.2021", amount: "1.04 FOIL" },
        { type: "Withdrawal of funds", date: "02.06.2021", amount: "4 FOIL" },
        { type: "Getting a token", date: "20.05.2021", amount: "1 FOIL" },
        { type: "Withdrawal of funds", date: "10.05.2021", amount: "1.4 FOIL" },
        { type: "Getting a token", date: "11.04.2021", amount: "2 FOIL" },
      ],
    };
  },
};
</script>

<style lang="scss">
.transactions {
  font-family: LabGrotesque, serif;
  font-style: normal;
  font-weight: 400;

  &__head {
    font-size: 18px;
    color: #3f465c;
    padding: 20px 24px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    /*display: grid;*/
    /*grid-template-columns: 220px 1fr 1fr;*/

    .type {
      min-width: 120px;
    }
  }

  &__line {
    width: 100%;
    height: 1px;
    background: #2c3243;
  }

  &__body {
    padding: 14px 24px 24px;
    font-size: 15px;
    /*display: grid;*/
    /*grid-template-columns: 220px 1fr 1fr;*/
    min-width: 132px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  &__col-1 {
    display: flex;
    flex-direction: column;
    gap: 20px;
    color: $color-primary;

    &--item:nth-child(2n) {
      color: $color-accent;
    }
  }

  &__col-2 {
    display: flex;
    flex-direction: column;
    gap: 20px;
    color: $color-white;
  }

  &__col-3 {
    text-align: end;
    display: flex;
    flex-direction: column;
    gap: 20px;
    font-family: adineuePROCyr, serif;
    color: $color-accent;

    &--item {
      background: gradient-accent(110deg, 70%, 95%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }
  }
}
</style>
