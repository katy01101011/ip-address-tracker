<template>
  <div id="app">
    <div class="app-body">
      <div class="app-top">
        <h1>IP Address Tracker</h1>
        <SearchBar @search="ipToFind" />
        <SearchInfo :position="position" />
      </div>
      <div class="app-bottom">
        <AppMap />
      </div>
    </div>
  </div>
</template>

<script>
import SearchBar from "./components/SearchBar.vue";
import SearchInfo from "./components/SearchInfo.vue";
import AppMap from "./components/AppMap.vue";

export default {
  name: "App",
  components: {
    SearchBar,
    SearchInfo,
    AppMap,
  },
  data() {
    return {
      ipToSearch: "",
      position: {
        ip: "192.212.174.101",
        location: "Brooklyn, NY",
        timezone: "UTC-05:00",
        isp: "SpaceX Starlink",
      },
    };
  },
  methods: {
    ipToFind(ip) {
      this.ipToSearch = ip;
      // "192.212.174.101"
      // console.log(this.ipToSearch);
    },
  },
};
</script>

<style lang="scss">
@import "@fortawesome/fontawesome-free/css/all.css";
@import "./style/variables.scss";

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

  .app-body {
    width: 100%;
    height: 100vh;

    .app-top {
      width: 100%;
      height: 35vh;
      background-image: url(../public/images/pattern-bg.png);
      background-size: cover;
      position: relative;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;

      h1 {
        color: white;
      }
    }

    .app-bottom {
      width: 100%;
      height: 65vh;
      background-color: lightgrey;
    }
  }
}
</style>
