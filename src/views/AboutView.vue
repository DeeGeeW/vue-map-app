<template>
  <body class="about-bg">
    <div class="about">
      <h1>Philly Philly</h1>
      <div id="map"></div>
      <br />
      <img
        src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRsQdqy6Y7MzAl4Zby6nnQLq-JDKYQMUmn_wA&usqp=CAU"
        alt=""
      />
    </div>
  </body>
</template>

<script>
/* global mapboxgl */
export default {
  data: function () {
    return {
      places: [],
    };
  },
  mounted: function () {
    this.getPlaces();
  },
  methods: {
    getPlaces() {
      // make axios
      this.places = [
        { lat: 39.9014, lng: -75.1, description: "The Link" },
        { lat: 39.844, lng: -75.0, description: "My childhood town" },
      ];
      this.setMap();
    },
    setMap() {
      mapboxgl.accessToken = process.env.VUE_APP_MAP_API_KEY;
      const map = new mapboxgl.Map({
        container: "map", // container ID
        style: "mapbox://styles/mapbox/dark-v10", // style URL
        center: [this.places[0].lng, this.places[0].lat], // starting position [lng, lat]
        zoom: 9, // starting zoom
      });
      this.places.forEach((place) => {
        // create the popup
        const popup = new mapboxgl.Popup({ offset: 25 }).setText(place.description);
        const marker = new mapboxgl.Marker().setLngLat([place.lng, place.lat]).setPopup(popup).addTo(map);
        console.log(map, marker);
      });
    },
  },
};
</script>

<style type="text/css">
body,
html {
  margin: 0;
  padding: 0;
  background-color: darkgreen;
  cursor: url("http://www.rw-designer.com/icon-image/12294-24x24x8.png"), auto;
}
/* body,
html :hover {
  cursor: url("http://www.rw-designer.com/cursor-view/110939.png"), auto;
} */
#map {
  height: 300px;
  width: 100%;
}
h1 {
  font-family: cursive;
  color: silver;
}
img {
  border-radius: 30%;
}
</style>
