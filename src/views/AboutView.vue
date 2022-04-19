<template>
  <div class="about">
    <h1>Philly Philly</h1>
    <div id="map"></div>
    <img src="" alt="" />
  </div>
</template>

<script>
/* global mapboxgl */
export default {
  data: function () {
    return {};
  },
  mounted: function () {
    mapboxgl.accessToken = process.env.VUE_APP_MAP_API_KEY;
    const map = new mapboxgl.Map({
      container: "map", // container ID
      style: "mapbox://styles/mapbox/dark-v10", // style URL
      center: [-74.5, 40], // starting position [lng, lat]
      zoom: 9, // starting zoom
    });
    console.log(map);
  },
  methods: {},
};
</script>

<style>
body {
  margin: 0;
  padding: 0;
  background-color: darkgreen;
}
#map {
  height: 300px;
  width: 100%;
}
h1 {
  color: silver;
}
</style>
