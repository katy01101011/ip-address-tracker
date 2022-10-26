<template>
  <div class="app-bottom">
    <div style="height: 100%; width: 100%">
      <l-map :zoom="zoom" :center="center" style="height: 100%">
        <l-tile-layer :url="url" :attribution="attribution" />
        <l-marker :lat-lng="withPopup">
          <l-popup>
            <p id="popupText">
              <!-- {{ test }} -->
              <!-- Popup -->
            </p>
          </l-popup>
        </l-marker>
      </l-map>
    </div>
    <!-- <div class="attribution">
      Challenge by
      <a href="https://www.frontendmentor.io?ref=challenge" target="_blank"
        >Frontend Mentor</a
      >. Coded by
      <a href="https://www.linkedin.com/in/karolina-tymoszuk/"
        >Karolina Tymoszuk</a
      >.
    </div> -->
  </div>
</template>

<script>
// import L from "leaflet";
import { LMap, LTileLayer, LMarker } from "vue2-leaflet";

export default {
  name: "AppMap",
  props: {
    isp: String,
  },
  data() {
    return {
      test: "Hello World!",
    };
  },
  components: {
    LMap,
    LTileLayer,
    LMarker,
  },
};
</script>

<script>
import { latLng, Icon } from "leaflet";
import { LMap, LTileLayer, LMarker, LPopup, LTooltip } from "vue2-leaflet";

delete Icon.Default.prototype._getIconUrl;
Icon.Default.mergeOptions({
  iconRetinaUrl: require("leaflet/dist/images/marker-icon-2x.png"),
  iconUrl: require("leaflet/dist/images/marker-icon.png"),
  shadowUrl: require("leaflet/dist/images/marker-shadow.png"),
});

export default {
  name: "AppMap",
  components: {
    LMap,
    LTileLayer,
    LMarker,
    LPopup,
    LTooltip,
  },
  data() {
    return {
      zoom: 16.5,
      center: latLng(43.731499, 7.414951),
      url: "https://tile.thunderforest.com/atlas/{z}/{x}/{y}.png?apikey=1f9c134dd3d14e259abe3ed390a4730f",
      attribution:
        '&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors',
      withPopup: latLng(43.731499, 7.414951),
      currentZoom: 20,
      currentCenter: latLng(43.731499, 7.414951),
      showParagraph: false,
      showMap: true,
    };
  },
};
</script>

<style></style>
