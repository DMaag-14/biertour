//Mapseite --> Mapbox richtig integrieren und scrolling machen
<template>
  <div class="about">
    <h1>This is the Map Page</h1>
    <div ref="container" class="map"></div>
    <div class="content">
      Text
    </div>
  </div>
</template>

<script>
import mapboxgl from "mapbox-gl";
//import contentfulClient from "@/modules/contentful.js";

export default {
  name: "Map",
  mounted: async function() {
    // Displaying the map
    mapboxgl.accessToken = "pk.eyJ1IjoiZG9taW1pIiwiYSI6ImNraGdlajhmdzByNDcyemx1amF5N3J0aW0ifQ.5-eh6rSPcoJtLXmUCl5y1Q";
    var map = new mapboxgl.Map({
      container: this.$refs.container,
      style: "mapbox://styles/domimi/ckh7indru297z19qei8ealm5m", // stylesheet location
      center: [8.546385, 47.190093], // starting position [lng, lat]
      zoom: 15 // starting zoom
    });

    map.on('load', function() {
    
    });
 }
}
</script>

<style scoped lang="scss">
@import url("https://api.mapbox.com/mapbox-gl-js/v1.12.0/mapbox-gl.css");
.map {
  float: left;
  height: 100%;
  width: 50%;
  position: fixed;
}

.content {
  float: left;
  height: 100%;
  width: 50%;
}

</style>