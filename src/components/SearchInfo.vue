<template>
  <div class="search-info">
    <div class="ip-address">
      <h4>IP Address</h4>
      <p>
        {{ localization.ip }}
      </p>
    </div>
    <div class="location">
      <h4>Location</h4>
      <p>
        {{ localization.location.city }}
      </p>
    </div>
    <div class="timezone">
      <h4>Timezone</h4>
      <p>UTC{{ localization.location.timezone }}</p>
    </div>
    <div class="isp">
      <h4>ISP</h4>
      <p>
        {{ localization.isp }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "SearchInfo",
  props: {
    localization: Object,
  },
};
</script>

<style lang="scss" scoped>
.search-info {
  width: 70%;
  display: flex;
  justify-content: space-around;
  margin: auto;
  background-color: #ffffff;
  padding: 2rem;
  border-radius: 20px;
  position: absolute;
  bottom: 0;
  transform: translateY(50%);
  z-index: 1000000000;
}
</style>
