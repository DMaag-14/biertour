//Mapseite --> Mapbox richtig integrieren und scrolling machen
<template>
  <div class="about">
    <h1>This is the Map Page</h1>
    <div ref="container" class="map"></div>
    <div class="content">
      <div v-for="bar in bars" :key="bar">
        <Bar :barTitel="bar.fields.barTitel" :barBeschreibung="bar.fields.barBeschreibung" :barRandomFact="bar.fields.barRandomFact" :barLocation="bar.fields.barLocation" />
      </div>
    </div>
  </div>
</template>

<script>
import mapboxgl from "mapbox-gl";
import Bar from "@/components/Tour.vue";
import contentfulClient from "@/modules/contentful.js";
import getCoordinatesFromGpxFile from "@/modules/gpx-utilities.js";

export default {
  name: "Map",
  mounted: async function() {
    mapboxgl.accessToken = "pk.eyJ1IjoiZG9taW1pIiwiYSI6ImNraDNlcmN5cTA5b2QycnF5eTBoOHlxbjkifQ.Hrc4LbKoBzKq85tXedZ8SA";
    const map = new mapboxgl.Map({
      container: this.$refs.container,
      style: "mapbox://styles/domimi/ckhknfjr43zn119ldctqkon8y",
      center: [46.9479121, 7.4485031],
      zoom: 9
    });

    map.on("load", async function(){
      let result = await contentfulClient
      .getEntries({
        content_type: "bar"
      });
      let coordinates = await getCoordinatesFromGpxFile(
        result.items[0].fields.gpx.fields.file.url
      );
       map.addSource("route", {
        type: "geojson",
        data: {
          type: "Feature",
          geometry: {
            type: "LineString",
            coordinates: coordinates
          }
        }
       });
    });
  },

  components: {
    Bar
  },
  data: function() {
    return {
      bars: []
    };
  },
  created: async function() {
    let result = await contentfulClient
      .getEntries({
        content_type: "bar"
      });
    this.bars =  result.items;
  }
};
</script>

<style>
@import url("https://api.mapbox.com/mapbox-gl-js/v1.12.0/mapbox-gl.css");
.map {
  float: left;
  height: 60%;
  width: 30%;
  position: fixed;
  left: 10%;
}

.content {
  float: left;
  height: 100%;
  width: 49%;
  position: absolute;
  left: 51%;
}

</style>