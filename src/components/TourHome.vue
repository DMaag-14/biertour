<template>
  <div class="tour">
    <h2>
      {{tourTitel}}
    </h2>
    <p>
      {{tourBeschreibung}}
    </p>
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

</style>