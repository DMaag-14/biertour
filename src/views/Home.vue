// Startmenu der Webbseite
<template>
  <div class="home">
    <router-link to="/map">
      <div ref="container" class="tour"></div>
      <div v-for="tour in tours" :key="tour">
          <Tour :tourTitel="tour.fields.tourTitel" :tourBeschreibung="tour.fields.tourBeschreibung" />
      </div>
    </router-link>
  </div>
</template>

<script>
import Tour from "@/components/TourHome.vue";
import contentfulClient from "@/modules/contentful.js";

export default {
  
name: "home",
components: {
    Tour
  },
  data: function() {
    return {
      tours: []
    };
  },
  created: async function() {
    let result = await contentfulClient
      .getEntries({
        content_type: "tour"
      });
    this.tours =  result.items;
  }
}
</script>


// Hier CSS Elemente und Style für Home/Startseite
<style>

.tour {
  float: left;
  height: 50%;
  width: 50%;
  position: absolute;
  background-color: gray;
}

</style>
