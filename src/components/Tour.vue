<template>
  <div class="bar">
    <h2>
      {{barTitel}}
    </h2>
    <p>
      {{barBeschreibung}}
    </p>

    <h3>
          Random Fact
    </h3>
    <p>
      {{barRandomFact}}
    </p>
  </div>
</template>

<script>
export default {
  name: "Bar",
  props: {
    barTitel: String,
    barBeschreibung: String,
    barBild: String,
    barRandomFact: String,
    barLocation: Object,

  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.person {
  color: rgb(103, 189, 189);
  font-weight: bold;;
}
</style>