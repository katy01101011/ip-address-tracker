<template>
  <div class="search-bar">
    <input
      type="text"
      v-model="ipToSearch"
      placeholder="Search for any IP address"
    />
    <button @click="$emit('search', ipToSearch)">
      <i class="fa-solid fa-chevron-right"></i>
    </button>
  </div>
</template>

<script>
// import axios from "axios";

export default {
  name: "SearchBar",
  data() {
    return {
      ipToSearch: "",
      // "192.212.174.101"
    };
  },
  // methods: {
  // typedIP() {
  // axios
  //   .get("https://geo.ipify.org/api/v2/country,city?", {
  //     params: {
  //       apiKey: "at_8a1MRcKOkZqAroCzrjk2myoWTqPhw",
  //       ipAddress: this.ipToSearch,
  //     },
  //   })
  //   .then((response) => {
  //     this.localization = response.data;
  //     console.log(this.localization);
  //   });
  // console.log(this.ipToSearch);
  // },
  // },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.search-bar {
  height: 3rem;

  input {
    width: 30vw;
    height: inherit;
    border: none;
    padding-left: 1rem;
    border-radius: 10px 0 0 10px;
  }

  button {
    height: inherit;
    border: none;
    padding: 0 1.3rem;
    color: white;
    background-color: black;
    border-radius: 0 10px 10px 0;
  }
}
</style>
