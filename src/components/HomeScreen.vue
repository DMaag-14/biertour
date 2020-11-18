<template>
  <div class="startseite">
    <h1>
      {{titelStartseite}}
    </h1>
    <p>
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
    bildStartseite: String
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>