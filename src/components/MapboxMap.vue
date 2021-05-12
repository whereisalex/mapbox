<template>
  <MglMap :accessToken="accessToken" :mapStyle="mapStyle">
    <MglMarker v-for="member in members" v-bind:key="member.id" :coordinates="[member.lat, member.long]" >
      <MglPopup>
          <div><img :src="member.image" :alt="member.firstName" /> <span>{{ member.firstName }} {{ member.lastName }}</span></div>
      </MglPopup>
    </MglMarker>
  </MglMap>
</template>

<script>
import Mapbox from "mapbox-gl";
import { MglMap, MglMarker, MglPopup } from "vue-mapbox";
import members from "../constants/user";

export default {
  components: {
    MglMap, MglMarker, MglPopup
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