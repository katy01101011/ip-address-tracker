<template>
  <div class="app-bottom">
    <div style="height: 100%; width: 100%">
      <l-map :zoom="zoom" :center="center" style="height: 100%">
        <l-tile-layer :url="url" :attribution="attribution" />
        <l-marker :lat-lng="withPopup">
          <l-popup>
            <div>
              I am a popup
              <p v-show="showParagraph">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque
                sed pretium nisl, ut sagittis sapien. Sed vel sollicitudin nisi.
                Donec finibus semper metus id malesuada.
              </p>
            </div>
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
      zoom: 13,
      center: latLng(47.41322, -1.219482),
      url: "https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",
      attribution:
        '&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors',
      withPopup: latLng(47.41322, -1.219482),
      currentZoom: 10,
      currentCenter: latLng(47.41322, -1.219482),
      showParagraph: false,
      showMap: true,
    };
  },
};
</script>

<style></style>
