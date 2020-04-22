<template>
  <div class="chartcontainer">
    <h2>Timeline</h2>
    <client-only>
      <line-chart v-if="data.datasets[0].data.length>0" :chart-data="data" :options="options"></line-chart>
      <template v-else>No Data to display</template>
    </client-only>
  </div>
</template>

<script>
import LineChart from "./charts/LineChart.js";

export default {
  name: "Chart",
  components: {
    LineChart
  },
  data() {
    return {
      datacollection: null,
      options: {
        responsive: true,
        legend: {
          display: false
        }
      }
    };
  },
  props: ["data"]
};
</script>

<style scoped lang="scss">
.chartcontainer {
  max-width: 100%;

  height: auto;
  text-align: center;
  color: white;
  margin: 50px 0;

  h2 {
    font-size: 2rem;
    padding: 10px 0;
  }
}
</style>