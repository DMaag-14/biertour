<template>
  <div class="home">
    <div v-for="commute in commutes" :key="commute.person">
      <Commute :person="commute.fields.commuter" :start="commute.fields.startLocationName" :destination="commute.fields.endLocationName" />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Commute from "@/components/Commute.vue";
import contentfulClient from "@/modules/contenful.js";

export default {
  name: "Home",
  components: {
    Commute
  },
  data: function() {
    return {
      commutes: []
    };
  },
  created: async function() {
    let result = await contentfulClient
      .getEntries({
        content_type: "commute"
      });
    this.commutes =  result.items;
  }
};
</script>
