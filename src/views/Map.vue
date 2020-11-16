//Mapseite --> Mapbox richtig integrieren und scrolling machen
<template>
  <div class="about">
    <h1>This is the Map Page</h1>
    <div ref="container" class="map"></div>
    <div class="content">
      Text für Content
    </div>
  </div>
</template>

<script>
import mapboxgl from "mapbox-gl";
//import contentfulClient from "@/modules/contentful.js";

export default {
  name: "Map",
  mounted: async function() {
    mapboxgl.accessToken = "pk.eyJ1IjoiZG9taW1pIiwiYSI6ImNraDNlcmN5cTA5b2QycnF5eTBoOHlxbjkifQ.Hrc4LbKoBzKq85tXedZ8SA";
    const map = new mapboxgl.Map({
      container: this.$refs.container,
      style: "mapbox://styles/domimi/ckhknfjr43zn119ldctqkon8y",
      center: [-93.261, 44.971],
      zoom: 15
    });

    map.on("load", async function(){

    });
  }

}
</script>

<style>
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
  position: absolute;
  left: 50%;
}

</style>