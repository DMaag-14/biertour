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
    </div>
    
  </div>
</template>

<script>
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
  height: 500px;
  position: relative;
  display: block;
  background-color: #333;
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
  color: var(--yellow-tint-20);
  bottom: 0%;
  left: -1%;
  line-height: 130%;
}

img.bar__header__logo {
  position: absolute;
  transform-origin: top right;
  right: -20%;
  top: 10%;
  transform: scale(0.8);
}

.section-grid.bar__body p {
  grid-column-start: 1;
  grid-column-end: 6;
  padding: 40px 0px;
}

</style>