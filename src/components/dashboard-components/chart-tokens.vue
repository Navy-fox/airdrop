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
      <svg
        style="width: 0; height: 0; position: absolute"
        aria-hidden="true"
        focusable="false"
      >
        <linearGradient id="my-gradient" x2="1" y2="1">
          <stop offset="0%" stop-color="#447799" />
          <stop offset="50%" stop-color="#224488" />
          <stop offset="100%" stop-color="#112266" />
        </linearGradient>
      </svg>
      <GChart
        type="ColumnChart"
        :data="chartData"
        :options="chartOptions"
        @ready="chr"
        @select="chr"
        @onmouseover="chr"
        @onmouseout="chr"
      />
    </div>
  </DashboardBlock>
</template>

<script>
import DashboardBlock from "./dashboard-block";
import { GChart } from "vue-google-charts";
import { CHARTS_TEST_DATA } from "../../data/CHARTS_TEST_DATA";

//TODO графики полная хрень. Нужно переделывать

export default {
  name: "chart-tokens",
  // eslint-disable-next-line vue/no-unused-components
  components: { DashboardBlock, GChart },
  computed: {
    chartDatat() {
      const join = this.isJoined;
      const chartData = [];
      chartData.push(Object.keys(CHARTS_TEST_DATA[0]));
      if (join.day) {
        CHARTS_TEST_DATA.forEach((i) => {
          const dateNow =
            new Date().getDate() + "." + (Number(new Date().getMonth()) + 1);
          if (i.date === String(dateNow)) {
            chartData.push(Object.values(i));
          }
        });
        // eslint-disable-next-line no-empty
      }
      return chartData;
    },
  },
  mounted() {
    console.log(
      new Date().getDate() + "." + (Number(new Date().getMonth()) + 1)
    );
  },
  data() {
    return {
      isJoined: {
        year: false,
        month: true,
        day: false,
      },
      chartData: [
        ["date", "mainFoil", "bonusFoil"],
        ["1.09", 1.7, 0],
        ["2.09", 1, 0],
        ["3.09", 1.7, 0],
        ["4.09", 1.8, 0],
        ["5.09", 2.5, 0.5],
        ["6.09", 2.1, 0],
        ["7.09", 1.6, 0],
        ["8.09", 2, 0],
        ["9.09", 1.6, 0],
        ["10.09", 2.4, 0],
        ["11.09", 1.6, 0],
        ["12.09", 2.9, 0],
      ],
      chartOptions: {
        chart: {
          title: "Company Performance",
          subtitle: "Sales, Expenses, and Profit: 2014-2017",
        },
        backgroundColor: "none",
        colors: ["#21D4FD", "#E40ECF"],
        explorer: { axis: "horizontal" },
        isStacked: true,
        enableInteractivity: false,
        bar: {
          groupWidth: 20,
        },
        vAxis: {
          minorGridlines: {
            color: "none",
            count: 0,
          },
          gridlines: {
            color: "#252A36",
            count: 3,
          },
          textStyle: {
            color: "#FFFFFF",
            fontName: "LabGrotesque",
            fontSize: 12,
            bold: true,
          },
        },
        hAxis: {
          gridlines: {
            units: {
              days: { format: "DD/MM" },
            },
          },
          slantedText: true,
          textStyle: {
            color: "#FFFFFF",
            fontName: "LabGrotesque",
            fontSize: 10,
            bold: true,
          },
        },
        chartArea: { left: 30, top: 24, width: "90%", height: "75%" },
        legend: { position: "none" },
        tooltip: { trigger: "none" },
      },
    };
  },
  methods: {
    chr(ctx) {
      let chartColumns = ctx.container.getElementsByTagName("rect");
      setTimeout(() => {
        Array.prototype.forEach.call(chartColumns, (column) => {
          column.setAttribute("rx", 3);
          column.setAttribute("ry", 3);
        });
      }, 0);
    },
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
    padding: 16px 24px 20px;

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
  padding: 0 24px;

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
