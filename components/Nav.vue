<template>
  <div class="nav">
    <h1>COVID-19 Tracker</h1>
    <h3 v-if="!country">World Now</h3>
    <h3 v-if="country">{{country}} Now</h3>
  </div>
</template>

<script>
export default {
  name: "Nav",
  props: ["country"]
};
</script>

<style lang="scss" scoped>
.nav {
  width: 100%;
  height: 15vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  flex-direction: column;
  padding: 5rem 0;

  h1 {
    width: 80%;
    font-size: 3rem;
    color: white;
    z-index: 100;
  }
  h3 {
    color: white;
  }
}
</style>