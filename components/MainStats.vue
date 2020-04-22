<template>
  <div class="flex">
    <div class="card cases">
      <div class="text">
        <svg xmlns="http://www.w3.org/2000/svg" class="heart" viewBox="0 0 24 24">
          <path
            d="M6.28 3c3.236.001 4.973 3.491 5.72 5.031.75-1.547 2.469-5.021 5.726-5.021 2.058 0 4.274 1.309 4.274 4.182 0 3.442-4.744 7.851-10 13-5.258-5.151-10-9.559-10-13 0-2.676 1.965-4.193 4.28-4.192zm.001-2c-3.183 0-6.281 2.187-6.281 6.192 0 4.661 5.57 9.427 12 15.808 6.43-6.381 12-11.147 12-15.808 0-4.011-3.097-6.182-6.274-6.182-2.204 0-4.446 1.042-5.726 3.238-1.285-2.206-3.522-3.248-5.719-3.248z"
          />
        </svg>
        <h3>Total Cases</h3>
      </div>

      <p>
        <animated-number
          :value="data.TotalConfirmed"
          :formatValue="formatToPrice"
          :duration="2000"
        />
      </p>
    </div>
    <div class="card deaths">
      <div class="text">
        <svg xmlns="http://www.w3.org/2000/svg" class="heart" viewBox="0 0 24 24">
          <path
            d="M15.582 19.485c-1.141 1.119-2.345 2.287-3.582 3.515-6.43-6.381-12-11.147-12-15.808 0-4.005 3.098-6.192 6.281-6.192 2.197 0 4.434 1.042 5.719 3.248 1.279-2.195 3.521-3.238 5.726-3.238 3.177 0 6.274 2.171 6.274 6.182 0 1.577-.649 3.168-1.742 4.828l-1.447-1.447c.75-1.211 1.189-2.341 1.189-3.381 0-2.873-2.216-4.182-4.274-4.182-3.257 0-4.976 3.475-5.726 5.021-.747-1.54-2.484-5.03-5.72-5.031-2.315-.001-4.28 1.516-4.28 4.192 0 3.442 4.742 7.85 10 13l2.168-2.121 1.414 1.414zm7.418-5.485h-8v2h8v-2z"
          />
        </svg>
        <h3>Total Deaths</h3>
      </div>

      <p>
        <animated-number :value="data.TotalDeaths" :formatValue="formatToPrice" :duration="2000" />
      </p>
    </div>
    <div class="card recovered">
      <div class="text">
        <svg xmlns="http://www.w3.org/2000/svg" class="heart" viewBox="0 0 24 24">
          <path
            d="M15.653 19.415c-1.162 1.141-2.389 2.331-3.653 3.585-6.43-6.381-12-11.147-12-15.808 0-4.005 3.098-6.192 6.281-6.192 2.197 0 4.434 1.042 5.719 3.248 1.279-2.195 3.521-3.238 5.726-3.238 3.177 0 6.274 2.171 6.274 6.182 0 1.269-.424 2.546-1.154 3.861l-1.483-1.484c.403-.836.637-1.631.637-2.377 0-2.873-2.216-4.182-4.274-4.182-3.257 0-4.976 3.475-5.726 5.021-.747-1.54-2.484-5.03-5.72-5.031-2.315-.001-4.28 1.516-4.28 4.192 0 3.442 4.742 7.85 10 13l2.239-2.191 1.414 1.414zm7.347-5.415h-3v-3h-2v3h-3v2h3v3h2v-3h3v-2z"
          />
        </svg>
        <h3>Total Recovered</h3>
      </div>
      <p>
        <animated-number
          :value="data.TotalRecovered"
          :formatValue="formatToPrice"
          :duration="1000"
        />
      </p>
    </div>
  </div>
</template>

<script>
import AnimatedNumber from "animated-number-vue";

export default {
  name: "MainStats",
  props: ["data"],
  components: {
    AnimatedNumber
  },
  methods: {
    formatToPrice(value) {
      return value.toFixed(0);
    }
  }
};
</script>

<style scoped lang="scss">
.flex {
  width: 80%;
  display: flex;
  justify-content: space-around;
  .card {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    border: 3px white solid;
    border-radius: 13px;
    width: unquote("min(90%, 300px)");
    height: 200px;
    margin: auto 20px;
    .text {
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      width: 100%;

      h3 {
        color: white;
      }
    }
    p {
      font-size: 2.5rem;
      color: white;
    }
  }
  .cases {
    border-color: lightgray;
    .heart {
      fill: lightgray;
      width: 20%;
    }
  }
  .deaths {
    border-color: rgb(197, 16, 16);
    .heart {
      fill: rgb(197, 16, 16);
      width: 20%;
    }
  }
  .recovered {
    border-color: rgb(17, 182, 17);
    .heart {
      fill: rgb(17, 182, 17);
      width: 20%;
    }
  }
}

@media only screen and (max-width: 760px) {
  .flex {
    width: 85%;
    display: block;
    .card {
      margin: 20px auto;
    }
  }
}
</style>