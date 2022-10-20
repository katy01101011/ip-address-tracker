<template>
  <div class="search-bar">
    <input type="text" placeholder="Search for any IP address or domain" />
    <!-- at_8a1MRcKOkZqAroCzrjk2myoWTqPhw -->
    <button>
      <i class="fa-solid fa-chevron-right"></i>
    </button>
  </div>
</template>

<script>
export default {
  name: "SearchBar",
  // props: {
  //   msg: String,
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
