<template>
  <DashboardBlock title="Airdrops history" class="history">
    <div class="history__head">
      <span class="name">Name</span>
      <span>Date</span>
      <span> Result </span>
    </div>
    <div class="history__line"></div>
    <div class="history__body">
      <div class="history__col-1">
        <div
          class="history__col-1 history__col-1--item"
          v-for="(i, k) in history"
          :key="k"
        >
          {{ i.name }}
        </div>
      </div>
      <div class="history__col-2">
        <div v-for="(i, k) in history" :key="k">
          {{ i.date }}
        </div>
      </div>
      <div class="history__col-3">
        <div
          class="history__col-3 history__col-3--item"
          v-for="(i, k) in history"
          :key="k"
        >
          {{ i.result }}
        </div>
      </div>
    </div>
  </DashboardBlock>
</template>

<script>
import DashboardBlock from "./dashboard-block";

export default {
  name: "airdrop-history",
  components: { DashboardBlock },
  data() {
    return {
      history: [
        {
          name: "Airdrop #1",
          date: "10.06.2021 - 10.06.2021",
          result: "1.04 FOIL",
        },
        {
          name: "Airdrop #2",
          date: "08.06.2021 - 08.07.2021",
          result: "1.04 FOIL",
        },
        {
          name: "Airdrop #3",
          date: "10.05.2021 - 10.06.2021",
          result: "1.04 FOIL",
        },
        {
          name: "Airdrop #4",
          date: "08.05.2021 - 08.06.2021",
          result: "1.04 FOIL",
        },
        {
          name: "Airdrop #5",
          date: "10.04.2021 - 10.05.2021",
          result: "1.04 FOIL",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
.history {
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

    .name {
      max-width: 120px;
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
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  &__col-1 {
    display: flex;
    flex-direction: column;
    gap: 20px;
    font-family: adineuePROCyr, serif;
    color: $color-accent;
    white-space: nowrap;

    &--item {
      background: gradient-accent(130deg, 10%, 25%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    @include mob() {
      gap: 43px;
    }
  }

  &__col-2 {
    display: flex;
    flex-direction: column;
    gap: 20px;
    color: $color-white;
    padding: 0 10px;
    white-space: pre-wrap;
  }

  &__col-3 {
    text-align: end;
    display: flex;
    flex-direction: column;
    gap: 20px;
    font-family: adineuePROCyr, serif;
    color: $color-accent;
    white-space: nowrap;

    &--item {
      background: gradient-accent(110deg, 70%, 95%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    @include mob() {
      gap: 43px;
    }
  }
}
</style>
