<template>
  <div class="map">
    <h1>This is the Map Page</h1>
    <div ref="container" class="map"></div>
  </div>
</template>

<script>
import mapboxgl from "mapbox-gl";
//import contentfulClient from "@/modules/contentful.js";

export default {
  name: "Map",
  mounted: async function() {
    // Displaying the map
    mapboxgl.accessToken = "pk.eyJ1IjoibWh1c20iLCJhIjoiY2tnY2MxdGQ1MHBrYzMxa3oyc3gxMzRiNyJ9.JPZ11U69h64ksO-S4xBZlw";
    
 }
}
</script>