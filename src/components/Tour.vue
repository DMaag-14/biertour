<template>
  <div class="section-bar">
    <div class="bar-header" style="background: url(''), #333">
      <h2>{{barTitel}}</h2>
      <p>{{barRandomFact}}</p>
      <img src="" alt="Bar Logo" class="bar-logo">
    </div>

    <div class="bar-body">
      <p>{{barBeschreibung}}</p>
    </div>
    
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
<!-- <style scoped lang="scss"> !-->
<style scoped >
.bar-header {
  height: 500px;
  position: relative;
}

.bar-header h2 {
  position: absolute;
  top: 0%;
  left: 5%;
}



</style>