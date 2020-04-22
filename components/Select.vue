<template>
  <div class="sideselect" :class="{'isopen':isOpen}">
    <div v-if="isloading" class="loader">
      <svg viewBox="0 0 464 464.30563" class="corona" xmlns="http://www.w3.org/2000/svg">
        <path
          d="m432.304688 200.152344c-11.386719.023437-21.890626 6.125-27.558594 16h-45.542969c-2.871094-22.738282-11.828125-44.277344-25.929687-62.34375l32.28125-32.273438c13.988281 3.75 28.75-2.367187 35.992187-14.910156 7.238281-12.542969 5.152344-28.386719-5.085937-38.625-10.242188-10.242188-26.085938-12.328125-38.628907-5.085938-12.539062 7.238282-18.65625 22-14.910156 35.992188l-32.273437 32.277344c-18.066407-14.101563-39.605469-23.058594-62.34375-25.925782v-45.546874c12.542968-7.238282 18.660156-22.003907 14.910156-35.992188-3.75-13.992188-16.425782-23.71875-30.910156-23.71875-14.484376 0-27.160157 9.726562-30.910157 23.71875-3.746093 13.988281 2.367188 28.753906 14.910157 35.992188v45.546874c-22.738282 2.867188-44.277344 11.824219-62.34375 25.925782l-32.269532-32.277344c3.746094-13.992188-2.371094-28.753906-14.914062-35.992188-12.542969-7.242187-28.386719-5.15625-38.625 5.085938-10.242188 10.238281-12.328125 26.082031-5.085938 38.625 7.238282 12.542969 22 18.660156 35.992188 14.910156l32.277344 32.273438c-14.097657 18.066406-23.058594 39.605468-25.925782 62.34375h-45.542968c-7.242188-12.542969-22.007813-18.65625-35.996094-14.910156-13.992188 3.75-23.71875 16.425781-23.71875 30.910156s9.726562 27.160156 23.71875 30.910156c13.988281 3.75 28.753906-2.367188 35.996094-14.910156h45.542968c2.867188 22.738281 11.828125 44.277344 25.925782 62.34375l-32.277344 32.273437c-13.992188-3.746093-28.753906 2.367188-35.992188 14.910157-7.242187 12.542968-5.15625 28.386718 5.085938 38.628906 10.238281 10.238281 26.082031 12.324218 38.625 5.085937 12.542968-7.242187 18.660156-22.003906 14.914062-35.992187l32.269532-32.28125c18.066406 14.101562 39.605468 23.058594 62.34375 25.925781v45.546875c-12.542969 7.242188-18.65625 22.003906-14.910157 35.992188 3.75 13.992187 16.425781 23.71875 30.910157 23.71875 14.484374 0 27.160156-9.726563 30.910156-23.71875 3.75-13.988282-2.367188-28.75-14.910156-35.992188v-45.546875c22.738281-2.867187 44.277343-11.824219 62.34375-25.925781l32.273437 32.28125c-3.746094 13.988281 2.371094 28.75 14.910156 35.992187 12.542969 7.238281 28.386719 5.152344 38.628907-5.085937 10.238281-10.242188 12.324218-26.085938 5.085937-38.628906-7.242187-12.542969-22.003906-18.65625-35.992187-14.910157l-32.28125-32.273437c14.101562-18.066406 23.058593-39.605469 25.929687-62.34375h45.542969c7.789062 13.398437 24.070312 19.273437 38.617187 13.933594 14.550781-5.339844 23.167969-20.347657 20.445313-35.605469-2.726563-15.253907-16.007813-26.355469-31.503906-26.328125zm0 0"
          fill="#ea4a3b"
        />
        <path
          d="m432.304688 200.152344c-11.386719.023437-21.890626 6.125-27.558594 16h-45.542969c-2.871094-22.738282-11.828125-44.277344-25.929687-62.34375l32.28125-32.273438c13.230468 3.5625 27.261718-1.71875 34.855468-13.125 7.597656-11.40625 7.0625-26.390625-1.328125-37.222656-8.390625-10.835938-22.757812-15.105469-35.703125-10.609375-26.464844 128.117187-143.777344 203.460937-236.433594 243.878906 1.417969 2.046875 2.863282 4.070313 4.390626 6.039063l-32.277344 32.273437c-13.992188-3.746093-28.753906 2.367188-35.992188 14.910157-7.242187 12.542968-5.15625 28.386718 5.085938 38.628906 10.238281 10.238281 26.082031 12.324218 38.625 5.085937 12.542968-7.242187 18.660156-22.003906 14.914062-35.992187l32.269532-32.28125c18.066406 14.101562 39.605468 23.058594 62.34375 25.925781v45.546875c-12.542969 7.242188-18.65625 22.003906-14.910157 35.992188 3.75 13.992187 16.425781 23.71875 30.910157 23.71875 14.484374 0 27.160156-9.726563 30.910156-23.71875 3.75-13.988282-2.367188-28.75-14.910156-35.992188v-45.546875c22.738281-2.867187 44.277343-11.824219 62.34375-25.925781l32.273437 32.28125c-3.746094 13.988281 2.371094 28.75 14.910156 35.992187 12.542969 7.238281 28.386719 5.152344 38.628907-5.085937 10.238281-10.242188 12.324218-26.085938 5.085937-38.628906-7.242187-12.542969-22.003906-18.65625-35.992187-14.910157l-32.28125-32.273437c14.101562-18.066406 23.058593-39.605469 25.929687-62.34375h45.542969c7.789062 13.398437 24.070312 19.273437 38.617187 13.933594 14.550781-5.339844 23.167969-20.347657 20.445313-35.605469-2.726563-15.253907-16.007813-26.355469-31.503906-26.328125zm0 0"
          fill="#de4132"
        />
        <g fill="#fc685b">
          <path
            d="m256.304688 168.152344c0 13.253906-10.746094 24-24 24-13.253907 0-24-10.746094-24-24s10.746093-24 24-24c13.253906 0 24 10.746094 24 24zm0 0"
          />
          <path
            d="m256.304688 296.152344c0 13.253906-10.746094 24-24 24-13.253907 0-24-10.746094-24-24s10.746093-24 24-24c13.253906 0 24 10.746094 24 24zm0 0"
          />
          <path
            d="m184.304688 232.152344c0 13.253906-10.746094 24-24 24-13.253907 0-24-10.746094-24-24s10.746093-24 24-24c13.253906 0 24 10.746094 24 24zm0 0"
          />
          <path
            d="m328.304688 232.152344c0 13.253906-10.746094 24-24 24-13.253907 0-24-10.746094-24-24s10.746093-24 24-24c13.253906 0 24 10.746094 24 24zm0 0"
          />
        </g>
      </svg>
    </div>
    <div class="openclose" @click="isOpen=!isOpen">
      <svg
        version="1.1"
        class="arrow"
        viewBox="0 0 477.175 477.175"
        style="enable-background:new 0 0 477.175 477.175;"
        xml:space="preserve"
      >
        <g>
          <path
            d="M145.188,238.575l215.5-215.5c5.3-5.3,5.3-13.8,0-19.1s-13.8-5.3-19.1,0l-225.1,225.1c-5.3,5.3-5.3,13.8,0,19.1l225.1,225
		c2.6,2.6,6.1,4,9.5,4s6.9-1.3,9.5-4c5.3-5.3,5.3-13.8,0-19.1L145.188,238.575z"
          />
        </g>
      </svg>
      List
    </div>
    <div class="container">
      <div class="expand">
        <input
          type="text"
          class="search"
          placeholder="Search a Country..."
          @input="filter()"
          v-model="search"
        />
        <div class="border"></div>
      </div>
      <div class="filter">
        <div class="name" @click="sortbyName">
          <p>by name</p>
        </div>
        <div class="cases" @click="sortbyCases">
          <p>by cases</p>
        </div>
      </div>

      <div class="scrollable">
        <div class="card">
          <div
            class="itemdata"
            @click="()=>{$emit('get',global.slug);$emit('countryName','World');isOpen=!isOpen}"
          >
            <p class="name">Global</p>
            <p class="cases">{{global.cases}}</p>
          </div>
        </div>
        <div class="card" v-for="country,i in countries" :key="i">
          <div
            class="itemdata"
            @click="()=>{$emit('get',country.slug);$emit('countryName',country.name);isOpen=!isOpen}"
          >
            <p class="name">{{country.name}}</p>
            <p class="cases">{{country.cases}}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Vuetable from "vuetable-2";
export default {
  name: "Select",
  components: {
    Vuetable
  },
  data() {
    return {
      global: {},
      countries: [],
      origin: [],
      search: "",
      isOpen: false,
      byName: false,
      byCases: false,
      isloading: true
    };
  },
  async mounted() {
    let { data } = await this.$axios.get("https://api.covid19api.com/summary");
    this.global = {
      name: data.Global,
      cases: data.Global.TotalConfirmed,
      slug: "global"
    };
    console.log("HEEERE", this.global);
    data.Countries.forEach(coun => {
      this.countries.push({
        name: coun.Country,
        cases: coun.TotalConfirmed,
        slug: coun.Slug
      });
    });
    this.origin = this.countries;
    this.isloading = false;
  },
  methods: {
    filter() {
      console.log("changinh");
      if (!this.search) {
        this.countries = this.origin;
      } else {
        console.log(this.search);
        this.countries = this.countries.filter(el =>
          el.name.toLowerCase().includes(this.search.toLowerCase())
        );
        console.log(this.countries);
      }
    },
    sortbyName() {
      if (!this.byName) {
        this.countries.sort((a, b) => {
          if (a.name > b.name) {
            return -1;
          }
          if (a.name < b.name) {
            return 1;
          }
          return 0;
        });
        this.byName = !this.byName;
      } else {
        this.countries.reverse();
        this.byName = !this.byName;
      }
    },
    sortbyCases() {
      if (!this.byCases) {
        this.countries.sort((a, b) => {
          if (a.cases > b.cases) {
            return -1;
          }
          if (a.cases < b.cases) {
            return 1;
          }
          return 0;
        });
        this.byCases = !this.byCases;
      } else {
        this.countries.reverse();
        this.byCases = !this.byCases;
      }
    }
  }
};
</script>

<style scoped lang="scss">
/* width */
::-webkit-scrollbar {
  display: none;
}
.isopen {
  left: 0 !important;
  transition: left 0.2s ease;
}
.sideselect {
  transition: left 0.2s ease;
  position: fixed;
  top: 0;
  left: -300px;
  height: 100vh;
  width: 300px;
  background: #272727;
  color: lightgrey;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 101;
  .loader {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100vh;
    background: #333;
    z-index: 1000;
    display: flex;
    justify-content: center;
    align-items: center;
    .corona {
      width: 100px;
      animation: rotate 1s infinite;
    }
    @keyframes rotate {
      0%,
      50% {
        transform: rotate(180deg);
      }
      50%,
      100% {
        transform: rotate(360deg);
      }
    }
  }

  .openclose {
    z-index: 50;
    position: absolute;
    width: 50px;
    height: 60px;
    top: 0;
    right: -50px;
    display: flex;
    align-items: center;
    cursor: pointer;
    text-align: center;
    background: #333;
    border-radius: 10px;
    .arrow {
      width: 30px;
      fill: white;
    }
  }

  .container {
    height: 100%;
    width: 100%;
    .expand {
      position: relative;

      .border {
        display: block;
        position: absolute;
        height: 3px;
        width: 100%;
        top: 100%;
        background: salmon;
        transform: scaleX(0);
        transition: transform 0.3s;
        transform-origin: 50% 50%;
      }
      input:focus + .border,
      &:focus .border {
        transform: scaleX(1);
      }
      .search {
        width: 100%;
        height: 50px;
        padding: 0 20px;
        color: lightgrey;
        text-align: center;
        background: #272727;
        font-size: 1rem;
        border: none;
        outline: none;
      }
    }
    .filter {
      display: flex;
      border-top: 1px rgba(0, 0, 0, 0.096) solid;
      align-items: center;

      div {
        flex: 1;
        text-align: center;
        p {
          padding: 10px 0;
        }
        cursor: pointer;
        &:after {
          display: block;
          content: "";
          border-bottom: salmon 3px solid;
          transform: scaleX(0);
          transition: transform 0.3s;
        }
        border-left: 1px rgba(0, 0, 0, 0.096) solid;

        &:hover:after {
          transform: scaleX(1);
        }
      }
    }
    .scrollable {
      overflow-y: scroll;
      width: 100%;
      height: calc(100vh - 100px);
      .card {
        height: 50px;
        width: 100%;
        padding: 5px 20px;
        .itemdata {
          display: flex;
          align-items: center;
          justify-content: space-between;
          p {
            font-size: 1rem;
          }
          .name {
            flex: 2;
          }
          .cases {
            flex: 1;
            text-align: center;
          }
        }
        transition: 0.3s transform ease;
        cursor: pointer;
      }
      .card:hover {
        transform: scale(1.05);
        transition: 0.3s transform ease;
      }
    }
  }
}
</style>