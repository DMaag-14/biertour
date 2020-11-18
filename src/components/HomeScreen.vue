<template>
  <div class="tour">
    <h1>
      {{titelStartseite}}
    </h1>
    <p>
      {{tourBeschreibung}}
    </p>
  </div>
</template>

<script>
export default {
  name: "Startseite",
  props: {
    titelStartseite: String,
    }

  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>