<template>
  <DashboardBlock title="Total tokens received" class="chart-tokens">
    <div class="balance">
      <img src="icon/logo-circle.svg" alt="" class="balance-main__img" />
      <span class="heading heading--h2 heading--grad-revert">0.22045</span>
      <p class="heading heading--desc">FOIL</p>
    </div>
    <div class="chart-head">
      <p class="chart-head__title">Chart</p>
      <div class="chart-head__date-chips">
        <button
          type="button"
          class="chart-head__chips"
          :class="{ 'chart-head__chips--joined': isJoined.year }"
          @click="
            isJoined.day = false;
            isJoined.month = false;
            isJoined.year = true;
          "
        >
          Year
        </button>
        <button
          type="button"
          class="chart-head__chips"
          :class="{ 'chart-head__chips--joined': isJoined.month }"
          @click="
            isJoined.day = false;
            isJoined.month = true;
            isJoined.year = false;
          "
        >
          Month
        </button>
        <button
          type="button"
          class="chart-head__chips"
          :class="{ 'chart-head__chips--joined': isJoined.day }"
          @click="
            isJoined.day = true;
            isJoined.month = false;
            isJoined.year = false;
          "
        >
          Day
        </button>
      </div>
    </div>
    <div class="chart-body">
      <GChart type="ColumnChart" :data="chartData" :options="chartOptions" />
    </div>
  </DashboardBlock>
</template>

<script>
import DashboardBlock from "./dashboard-block";
import { GChart } from "vue-google-charts";

export default {
  name: "chart-tokens",
  // eslint-disable-next-line vue/no-unused-components
  components: { DashboardBlock, GChart },
  data() {
    return {
      isJoined: {
        year: false,
        month: false,
        day: true,
      },
      chartData: [
        ["Year", "Sales", "Expenses", "Profit"],
        ["2014", 1000, 400, 200],
        ["2015", 1170, 460, 250],
        ["2016", 660, 1120, 300],
        ["2017", 1030, 540, 350],
      ],
      chartOptions: {
        chart: {
          title: "Company Performance",
          subtitle: "Sales, Expenses, and Profit: 2014-2017",
        },
      },
    };
  },
};
</script>

<style lang="scss">
.chart-tokens {
  .balance {
    display: flex;
    align-items: baseline;
    justify-content: start;
    gap: 10px;
    padding: 25px 24px;

    &__img {
      width: 37px;
      height: 37px;
    }

    .heading {
      line-height: 100%;
    }
  }
}

.chart-head {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 24px 24px;

  &__title {
    font-family: LabGrotesque, serif;
    font-style: normal;
    font-weight: 400;
    color: $color-white;
    font-size: 16px;
  }

  &__date-chips {
    display: flex;
    gap: 7px;
  }

  &__chips {
    background: #0c111d;
    border: 1px solid #2c3243;
    border-radius: 6px;
    width: 65px;
    height: 30px;
    cursor: pointer;

    font-size: 12px;
    font-family: LabGrotesque, serif;
    font-style: normal;
    font-weight: 400;
    color: $color-white;

    &--joined {
      border: none;
      background: gradient-accent(110deg, -6%, 76%);
    }
  }
}
</style>