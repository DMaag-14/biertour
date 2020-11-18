//Mapseite --> Mapbox richtig integrieren und scrolling machen
<template>
  <div class="layout-container">
    <div ref="container" class="map"></div>
    <div class="content">
      <div class="section-grid">
        <h1>Altstadttour</h1>
        <p>Im Jahr 1191 wurde die Stadt Bern auf der Halbinsel, umgeben von der Aareschlaufe, von Herzog Berchtold V. von Zähringen gegründet. Die Zähringerstadt wurde ab 1200 etappenweise vergrössert: Im ersten Schritt von der Burg Nydegg bis zum Zytglogge (Zeitglockenturm), danach folgte die Stadterweiterung bis zum Käfigturm und noch etwas später kamen der Nydeggstalden und die Mattenenge hinzu.</p>
      </div>
      <div v-for="bar in bars" :key="bar">
        <Bar :barSubtitel="bar.fields.barSubtitel" :barTitel="bar.fields.barTitel" :barBeschreibung="bar.fields.barBeschreibung" :barRandomFact="bar.fields.barRandomFact" :barLocation="bar.fields.barLocation" />
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
    mapboxgl.accessToken = "pk.eyJ1Ijoic2NoYWVuZ3UiLCJhIjoiY2toM2U3dWhtMDB0MjJ5cXYzYThrcXM3cSJ9.o8sv3FDmYG7dNk-0JXVBhw";
    const map = new mapboxgl.Map({
      container: this.$refs.container,
      style: "mapbox://styles/schaengu/ckhg2ts590dms19ozwe4g7cuw",
      center: [7.4485031, 46.9479121],
      pitch: 60, 
      bearing: 60,
      zoom: 16
    });

    // DARK MAP
    // "pk.eyJ1IjoiZG9taW1pIiwiYSI6ImNraDNlcmN5cTA5b2QycnF5eTBoOHlxbjkifQ.Hrc4LbKoBzKq85tXedZ8SA"
    // "mapbox://styles/domimi/ckhknfjr43zn119ldctqkon8y"

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

.layout-container {
  display: block;
  width: 100%;
}

@import url("https://api.mapbox.com/mapbox-gl-js/v1.12.0/mapbox-gl.css");
.map {
  height: 100vh;
  width: 35%;
  display: block;
  position: fixed;
}

.content {
  display: flex;
  flex-direction: column;
  width: 60%;
  margin-left: 40%;
}

.section-grid {
  display: grid;
  grid-template-columns: repeat(8, 1fr);
  padding-right: 8%;
}

.section-grid h1{
  grid-column-start: 1;
  grid-column-end: -1;
}

.section-grid p {
  grid-column-start: 4;
  grid-column-end: -1;
}

</style>