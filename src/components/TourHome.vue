<template> 
  <div class="startseite-tour">
    <h4>{{tourTitel}}</h4>
    <p>{{tourKurzbeschrieb}}</p>
    <router-link to="/map"><button type="button">Tour ansehen</button></router-link>
  </div>
</template>

<script>
export default {
  name: "Tour",
  props: {
    tourTitel: String,
    // tourBeschreibung: String,
    tourKurzbeschrieb: String,
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .startseite-tour{
    background-color: #fff;
    box-shadow: 0px 4px 8px rgba(19, 19, 23, 0.4);
    padding: 3vh 5vh;
  }

  .startseite-tour h4{
    margin: 0;
  }
  
  button{
    background-color: var(--yellow-default);
    padding: 15px 15px;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    border: none;
    cursor: pointer;
  }
</style>