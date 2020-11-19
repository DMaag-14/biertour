<template>
  <div class="bar">
    <div class="section-full bar__header" :style="{ backgroundImage: `url(${barBild.fields.file.url})` }">
      <div class="bar__header__text">
        <p class="bar__header__stop">{{barSubtitel}}</p>
        <h2>{{barTitel}}</h2>
      </div>
      <p class="bar__header__random-fact">{{barRandomFact}}</p>
      <img :src="barLogo.fields.file.url" alt="Bar Logo" class="bar__header__logo" />
    </div>
    <div class="section-grid bar__body">
      <p>{{barBeschreibung}}</p>
      <!-- <p>{{bier[0].fields.bierTitel}}</p> -->
    </div>
    <div class="bier__grid">
      <div v-for="bier in biere" :key="bier">
          <Bier :bierTitel="barBierReferenz[0].fields.bierTitel" :bierAlkohol="barBierReferenz[0].fields.bierAlkohol" :bierHerkunft="barBierReferenz[0].fields.bierHerkunft" :bierArt="barBierReferenz[0].fields.bierArt" :bierBrauerei="barBierReferenz[0].fields.bierBrauerei" />
      </div>
    </div>
  </div>
</template>

<script>

import Bier from "@/components/Bier.vue";
import contentfulClient from "@/modules/contentful.js";

export default {
  name: "Bar",
  props: {
    barTitel: String,
    barBeschreibung: String,
    barBild: Object,
    barRandomFact: String,
    barLocation: Object,
    barSubtitel: String,
    barLogo: Object,
    barBierReferenz: Array
  },
  components: {
    Bier
  },
  data: function() {
    return {
      biere: []
    };
  },
  created: async function() {
    let result = await contentfulClient
      .getEntries({
        content_type: "bier"
      });
    this.biere = result.items;
  }
};

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<!-- <style scoped lang="scss"> !-->
<style scoped >

.bar {
  margin: 200px 0px;
}

.bar__header {
  height: 600px;
  position: relative;
  display: block;
  background-color: #333;
  background-size: cover;
  filter: saturate(0.3);
}

.bar__header::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  background: linear-gradient(180deg, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8));
  z-index: 1000;
}

.bar__header__text {
  position: absolute;
  top: -12%;
  left: 5%;
}

.bar__header .bar__header__text h2 {
  text-shadow: 0px 4px 8px rgba(19, 19, 23, 0.4);
  margin: 0;
}

.bar__header .bar__header__text .bar__header__stop {
  text-transform: uppercase;
  font-size: 1rem;
  color: var(--black-default-60);
  margin: 0;
}

.bar__header .bar__header__random-fact {
  position: absolute;
  transform-origin: bottom left;
  transform: rotate(-90deg);
  max-width: 450px;
  font-size: .875rem;
  color: var(--yellow-tint-60);
  bottom: 0%;
  left: -1%;
  line-height: 130%;
}

img.bar__header__logo {
  position: absolute;
  transform-origin: center center;
  right: -40%;
  top: 40%;
  transform: scale(0.8) rotate(-6deg);
  opacity: 0.6;
}

.section-grid.bar__body p {
  grid-column-start: 1;
  grid-column-end: 6;
  padding: 40px 0px;
  z-index: 2000;
  color: var(--black-default-20);
}

</style>