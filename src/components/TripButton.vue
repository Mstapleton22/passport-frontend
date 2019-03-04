<template>
  <div>
    <button v-on:click="trips.description + 1">Next</button>
  </div>
</template>
<script>
import TravelerProfile from "../views/TravelerProfile.vue";
import Trips from "../views/Trips.vue";

export default {
  data: {
    trips: {
      description: ""
    }
  }
};
</script>
<style>
</style>