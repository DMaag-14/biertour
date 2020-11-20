<template>
  <div class="startseite">
    <!-- <div class="bgImg" :style="{ backgroundImage: `url(${bildStartseite.fields.file.url})` }"></div> -->
    <p class="subtitelStartseite">
      {{subtitelStartseite}}
    </p>
    <h1>
      {{titelStartseite}}
    </h1>
    <p class="leadStartseite">
      {{leadStartseite}}
    </p>
  </div>
</template>

<script>
export default {
  name: "Startseite",
  props: {
    titelStartseite: String,
    subtitelStartseite: String,
    leadStartseite: String,
    bildStartseite: Object
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

/* .bgImg{
  width: 100vw;
} */

h1{
  margin: 0;
}
.startseite{
  margin-bottom: 4%;
}
.leadStartseite{
  width:40%;
}

.subtitelStartseite{
  margin-bottom: 0%;
  text-transform: uppercase;
}
</style>