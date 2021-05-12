<template>
  <MglMap :accessToken="accessToken" :mapStyle="mapStyle">
    <MglMarker v-for="member in members" v-bind:key="member.id" :coordinates="[member.long, member.lat]" >
      <MglPopup>
        <MapCard :member="member" />
      </MglPopup>
    </MglMarker>
  </MglMap>
</template>

<script>
import Mapbox from "mapbox-gl";
import { MglMap, MglMarker, MglPopup } from "vue-mapbox";
import MapCard from './MapCard';
import members from "../constants/user";

export default {
  components: {
    MglMap, MglMarker, MglPopup, MapCard
  },
  data() {
    return {
      accessToken: process.env.VUE_APP_MAPBOX_TOKEN,
      mapStyle: process.env.VUE_APP_MAPBOX_STYLE_URL,
    };
  },

  created() {
    this.members = members;
    this.mapbox = Mapbox;
  }
};
</script>
<style>
.mapboxgl-popup-content{
  padding: 10px;
}
</style>