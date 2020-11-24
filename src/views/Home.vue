// Startmenu der Webseite
<template>
  <div class="background">
      <div class="container home">
        <div ref="container" class="startseite-container">
            <div v-for="startseite in startseiten" :key="startseite">
              <Startseite :titelStartseite="startseite.fields.titelStartseite" :leadStartseite="startseite.fields.leadStartseite" :subtitelStartseite="startseite.fields.subtitelStartseite" />
            </div>
        </div> 

        <div ref="container" class="startseite-tour-container">
            <div v-for="tour in tours" :key="tour.fields.tourTitel">
              <Tour :tourTitel="tour.fields.tourTitel" :tourBeschreibung="tour.fields.tourBeschreibung" :tourKurzbeschrieb="tour.fields.tourKurzbeschrieb" />
            </div>
        </div>
      </div>
    <div class="bg-img"></div>
  </div>
</template>

<script>
import Startseite from "@/components/HomeScreen.vue";
import Tour from "@/components/TourHome.vue";
import contentfulClient from "@/modules/contentful.js";

export default {
  
name: "home",
components: {
    Startseite,
    Tour
  },
  data: function() {
    return {
      startseiten: [],
      tours: []
    };
  },
  created: async function() {
    let result = await contentfulClient
      .getEntries({
        content_type: "startseite"
      });
    this.startseiten =  result.items;

    result = await contentfulClient
      .getEntries({
        content_type: "tour"
      });
    this.tours =  result.items;
  }
}
</script>


// Hier CSS Elemente und Style für Home/Startseite
<style>
.background {
  height: 100vh;
  background-color: var(--white);
  position: relative;
}

.bg-img {
  display: block;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 1;
  background: linear-gradient(180deg, rgba(0,0,0,0), rgba(0,0,0,0.8)), url('../assets/bg.jpg');
  filter: saturate(0.5);
  background-size: cover;
  background-repeat: no-repeat;
}

.startseite-tour-container{
  width: 100%;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 40px;
  color: var(--black-default);
  padding: 2rem 0;
}

.container.home{
  display: flex;
  flex-direction: column;
  z-index: 2;
  position: relative;
}

.startseite-container {
  height: 60vh;
  display: flex;
  align-items: flex-end;
  color: var(--white);
}

.tourHome{
  height: 200px;
}

</style>
