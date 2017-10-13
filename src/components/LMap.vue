<template>
  <div id="mapDiv"></div>
</template>

<script>
import * as L from 'leaflet';
export default {
  name: 'LMap',
  data () {
    return {

    }
  },
  mounted () {
    let map = L.map('mapDiv').setView([51.505, -0.09], 13);
    L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token={accessToken}', {
      attribution: 'Map data &copy; <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, <a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="http://mapbox.com">Mapbox</a>',
      maxZoom: 18,
      id: 'mapbox.streets',
      accessToken: 'pk.eyJ1IjoiandlcnRzIiwiYSI6ImNpajVzMmNlMTAwNnF1bWx2OHg5azJoYmsifQ.LPkXb6ZRNRnCs4d1dGUnVg'
    }).addTo(map);
  }
};
</script>

<style scoped>
  #mapDiv {
    top: 0;
    bottom: 0;
    height: 100%;
    width: 100%;
  }
</style>
