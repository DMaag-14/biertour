// Startmenu der Webbseite
<template>
  <div class="home">
    <div ref="container" class="startseite-container">
        <div v-for="startseite in startseiten" :key="startseite">
            <Startseite :titelStartseite="startseite.fields.titelStartseite" :leadStartseite="startseite.fields.leadStartseite" :subtitelStartseite="startseite.fields.subtitelStartseite" />
        </div>
    </div> 
    <router-link to="/map">
    <div ref="container" class="tourHome">
          <div v-for="tour in tours" :key="tour">
            <Tour :tourTitel="tour.fields.tourTitel" :tourBeschreibung="tour.fields.tourBeschreibung" />
          </div>
    </div>
     <!-- <div class="startseite-tour-container">
        <div class="startseite-tour">
          <h3>Altstadttour</h3>
          <p>Das Hier wär när d Beschribig</p>
        </div>
        <div class="startseite-tour">
          <h3>Abendspaziergang</h3>
        </div>
     </div> -->
    </router-link>
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
        content_type: "tours"
      });
    this.tours =  result.items;
  }
}
</script>


// Hier CSS Elemente und Style für Home/Startseite
<style>
body{
  height: 100vh;
}

.home{
  display: flex;
  flex-direction: column;
  width: 90%;
  margin: 5%;
}

.startseite-container {
  background-color: rgb(139, 56, 56);
  height: 60vh;
  display:flex;
  align-items: flex-end;
 
}

.tourHome{
  height: 200px;
}

/* .startseite-tour-container{
  width: 100%;
  display: flex;
  flex-wrap: wrap;
}

.startseite-tour{
  background-color: #fff;
  flex-grow: 1;
}

.startseite-tour:nth-child(odd){
  margin-right: 2%;
} */

</style>
