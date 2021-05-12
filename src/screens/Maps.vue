<template>
  <div class="page-wrapper">
    <h3>mapbox</h3>
    <div class="map-wrapper">
      <MapboxMap/>
    </div>

    <h3>Google maps</h3>
      <div class="map-wrapper">
    </div>
  </div>
</template>

<script>
import MapboxMap from './../components/MapboxMap';

export default {
  components: {
    MapboxMap
  },
  name: 'Maps',
}
</script>

<style scoped>
h3 {
  margin: 40px 0;
}

.map-wrapper {
  margin-left: auto;
  margin-right: auto;
  width: 90vw;
  height: 500px;
}
</style>
