<template>
  <div class="chartcontainer">
    <h2>Details</h2>
    <client-only>
      <div class="container">
        <Doughnut
          class="chart"
          v-if="data.datasets[0].data.length>0"
          :chart-data="data"
          :options="options"
        ></Doughnut>
        <template v-else>No Data to display</template>
      </div>
    </client-only>
  </div>
</template>

<script>
import Doughnut from "./charts/Doughnut";

export default {
  name: "DoughnutC",
  components: {
    Doughnut
  },
  data() {
    return {
      options: {
        responsive: true,
        maintainAspectRatio: false,
        animation: {
          animateRotate: true
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
  max-height: 600px;
  text-align: center;
  color: white;

  h2 {
    font-size: 2rem;
    padding: 10px 0;
  }
  margin-top: 50px;
  .container {
    width: 100%;
    height: 100%;
    margin: 0 auto;
  }
}
</style>