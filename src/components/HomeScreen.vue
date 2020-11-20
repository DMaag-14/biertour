<template>
  <div class="startseite">
    <!-- <div class="bgImg" :style="{ backgroundImage: `url(${bildStartseite.fields.file.url})` }"></div> -->
    <p class="subtitel__startseite">
      {{subtitelStartseite}}
    </p>
    <h1>
      {{titelStartseite}}
    </h1>
    <p class="lead__startseite">
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
.lead__startseite{
  max-width: 45%;
  font-size: 1.25rem;
  line-height: 140%;
}

.subtitel__startseite{
  font-size: 1rem;
  letter-spacing: 2px;
  margin-bottom: 0;
  text-transform: uppercase;
}
</style>