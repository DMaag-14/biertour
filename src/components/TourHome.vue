<template> 
  <div class="startseite-tour-container">
        <div class="startseite-tour">
          <h3>{{tourTitel}}</h3>
          <p>{{tourBeschreibung}}</p>
        </div>
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

  .startseite-tour-container{
  width: 100%;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 40px;
}

.startseite-tour{
  background-color: #fff;
  /* flex-grow: 1; */
}

.startseite-tour:nth-child(odd){
  margin-right: 2%;
}
</style>