<template>
  <div class="homeMenu">
   <h2>Map 1</h2>
   <h2>Map 2</h2>
  </div>
</template>

<script>
export default {
  name: "HomeMenu",
  props: {
    BierTour: String
  }

};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.person {
  color: rgb(103, 189, 189);
  font-weight: bold;
}
</style>