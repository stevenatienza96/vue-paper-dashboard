<template>
    <card class="card-map" title="Portal Map">
      <div class="map">
        <div id="mapid"></div>
      </div>
    </card>
</template>

<script>
import * as Vue2Leaflet from 'vue2-leaflet';
export default {
  mounted() {
  var map = L.map('mapid', {
    center: [		10.31672, 123.8907089],
    zoom: 6
});

 L.tileLayer('https://api.mapbox.com/styles/v1/{id}/tiles/{z}/{x}/{y}?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', {
		maxZoom: 18,
		attribution: 'Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, ' +
			'<a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, ' +
			'Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
		id: 'mapbox/streets-v11'
	}).addTo(map);
  L.PM.initialize({ optIn: true });
 // add leaflet-geoman controls with some options to the map
  map.pm.addControls({
  position: 'topleft',
  drawCircle: true,
});

  }
  
};
</script>
<style>
</style>
