// Startmenu der Webbseite
<template>
  <div class="home">
    <router-link to="/map">
      <div ref="container" class="startseite"></div>
      <div v-for="startseite in startseiten" :key="startseite">
          <Startseite :titelStartseite="startseite.fields.titelStartseite" :leadStartseite="startseite.fields.leadStartseite" />
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
      startseiten: []
    };
  },
  created: async function() {
    let result = await contentfulClient
      .getEntries({
        content_type: "startseite"
      });
    this.startseiten =  result.items;
  }
}
</script>


// Hier CSS Elemente und Style für Home/Startseite
<style>

.startseite {
  float: left;
  height: 50%;
  width: 50%;
  position: absolute;
  background-color: gray;
}

</style>
