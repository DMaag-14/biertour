// Startmenu der Webbseite
<template>
  <div class="home">
    <router-link to="/map">
      <div ref="container" class="tour"></div>
      <div v-for="startseite in startseite" :key="startseite">
          <Startseite :tourTitel="startseite.fields.titelStartseite" :tourBeschreibung="startseite.fields.leadStartseite" />
      </div>
    </router-link>
  </div>
</template>

<script>
import Startseite from "@/components/HomeScreen.vue";
import contentfulClient from "@/modules/contentful.js";

export default {
  
name: "home",
components: {
    Startseite
  },
  data: function() {
    return {
      startseite: []
    };
  },
  created: async function() {
    let result = await contentfulClient
      .getEntries({
        content_type: "startseite"
      });
    this.startseite =  result.items;
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
