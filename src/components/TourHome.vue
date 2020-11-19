<template> 
  <div class="startseite-tour">
    <h3>{{tourTitel}}</h3>
    <p>{{tourBeschreibung}}</p>
  </div>
</template>

<script>
export default {
  name: "Tour",
  props: {
    tourTitel: String,
    tourBeschreibung: String,
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>



.startseite-tour{
  background-color: #fff;
  /* flex-grow: 1; */
}
</style>