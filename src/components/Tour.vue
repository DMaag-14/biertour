<template>
  <div class="bar" :id="barTitel">
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
      <Bier :bierTitel="barBier1.fields.bierTitel" :bierAlkohol="barBier1.fields.bierAlkohol" :bierHerkunft="barBier1.fields.bierHerkunft" :bierArt="barBier1.fields.bierArt" :bierBrauerei="barBier1.fields.bierBrauerei" :bierNummer="1" />
      <Bier :bierTitel="barBier2.fields.bierTitel" :bierAlkohol="barBier2.fields.bierAlkohol" :bierHerkunft="barBier2.fields.bierHerkunft" :bierArt="barBier2.fields.bierArt" :bierBrauerei="barBier2.fields.bierBrauerei" :bierNummer="2" />
      <Bier :bierTitel="barBier3.fields.bierTitel" :bierAlkohol="barBier3.fields.bierAlkohol" :bierHerkunft="barBier3.fields.bierHerkunft" :bierArt="barBier3.fields.bierArt" :bierBrauerei="barBier3.fields.bierBrauerei" :bierNummer="3" />
    </div>
  </div>
</template>

<script>

import Bier from "@/components/Bier.vue";

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
    barBier1: Object,
    barBier2: Object,
    barBier3: Object
  },
  components: {
    Bier
  },
  data: function() {
    return {
      biere: []
    };
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

.bier__grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  width: 92%;
  gap: 0px 40px;
}

.bier__grid .bier:nth-of-type(2){
  margin-top: 60%;
}

.bier__grid .bier:nth-of-type(1) {
  grid-column: 2;
  grid-row: 1;
}

.bier__grid .bier:nth-of-type(2) {
  grid-column: 1;
  grid-row: 1;
}

.bier__grid .bier:nth-of-type(3) {
  grid-column: 2;
  grid-row: 2;
}

@media (min-width: 1450px) {

  .bier__grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    width: 92%;
    gap: 80px 40px;
  }

  .bier__grid .bier:nth-of-type(2){
    margin-top: 0;
  }

  .bier__grid .bier:nth-of-type(1) {
    grid-column: 1;
    grid-row: 1;
  }

  .bier__grid .bier:nth-of-type(2) {
    grid-column: 2;
    grid-row: 1;
  }

  .bier__grid .bier:nth-of-type(3) {
    grid-column: 1;
    grid-row: 2;
  }
}

</style>