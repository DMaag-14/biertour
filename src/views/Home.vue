// Startmenu der Webbseite
<template>
  <div class="home">
    <router-link to="/Map">
      <div class="map1">
      </div>
    </router-link>

    <router-link to="/NextContent">
      <div class="map2">
      </div>
    </router-link>
  </div>
</template>

<script>

</script>


// Hier CSS Elemente und Style für Home/Startseite

<style>

.map1 {
  float: left;
  height: 50%;
  width: 50%;
  position: absolute;
  background-color: lightgoldenrodyellow;
}

.map2 {
  float: left;
  height: 50%;
  width: 50%;
  background-color: gray;
  position: absolute;
  Left: 50%;
  
}

</style>
