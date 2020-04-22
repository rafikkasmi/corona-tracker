<template>
  <div class="stats">
    <MainStats :data="data" />
    <DoughnutC v-if="doughnutData.datasets.length" :data="doughnutData"></DoughnutC>
    <Chart v-if="showChart" :data="chartData" />
  </div>
</template>

<script>
import MainStats from "./MainStats";
import Chart from "./Chart";
import DoughnutC from "./DoughnutC";

export default {
  name: "Statistics",
  components: {
    MainStats,
    Chart,
    DoughnutC
  },
  data() {
    return {
      countries: [],
      data: {},
      globalData: {},
      doughnutData: { datasets: [] },
      chartData: {},
      showChart: false
    };
  },
  props: ["slug"],
  watch: {
    slug: {
      deep: true,
      async handler() {
        if (this.slug != "global") {
          let { data } = await this.$axios.get(
            `https://api.covid19api.com/total/country/${this.slug}`
          );
          const last = data[data.length - 1];
          if (data.length) {
            this.data = {
              TotalConfirmed: last.Confirmed,
              TotalDeaths: last.Deaths,
              TotalRecovered: last.Recovered
            };
          } else {
            this.data = {
              TotalConfirmed: 0,
              TotalDeaths: 0,
              TotalRecovered: 0
            };
          }
          this.showChart = true;
          let dates = data.map(coun => coun.Date.split("T")[0]);
          let confirmed = data.map(coun => coun.Confirmed);
          let deaths = data.map(coun => coun.Deaths);
          let recovered = data.map(coun => coun.Recovered);
          this.chartData = {
            labels: dates,
            datasets: [
              {
                label: "Confirmed",
                backgroundColor: "transparent",
                borderColor: "lightgrey",
                pointBackgroundColor: "transparent",
                pointBorderColor: "transparent",
                data: confirmed
              },
              {
                label: "Deaths",
                backgroundColor: "transparent",
                borderColor: "rgba(197, 16, 16,1)",
                pointBackgroundColor: "transparent",
                pointBorderColor: "transparent",
                data: deaths
              },
              {
                label: "Recovered",
                backgroundColor: "transparent",
                borderColor: "rgba(17, 182, 17,1)",
                pointBackgroundColor: "transparent",
                pointBorderColor: "transparent",
                data: recovered
              }
            ]
          };
          this.setChartWorld();
        } else {
          this.data = this.globalData;
          this.showChart = false;
          this.setChartWorld();
        }
      }
    }
  },

  async mounted() {
    let { data } = await this.$axios.get("https://api.covid19api.com/summary");
    this.data = data.Global;
    this.globalData = data.Global;
    this.setChartWorld();
  },
  methods: {
    setChartWorld() {
      this.doughnutData = {
        labels: ["Active", "Deaths", "Recovered"],
        datasets: [
          {
            backgroundColor: [
              "lightgrey",
              "rgba(197, 16, 16,1)",
              "rgba(17, 182, 17,1)"
            ],
            borderColor: "transparent",

            data: [
              this.data.TotalConfirmed -
                (this.data.TotalDeaths + this.data.TotalRecovered),
              this.data.TotalDeaths,
              this.data.TotalRecovered
            ]
          }
        ]
      };
    }
  }
};
</script>

<style lang="scss" scoped>
.stats {
  width: 100%;
  height: auto;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
</style>