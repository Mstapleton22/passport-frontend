<template>
  <div>
    <div class="cards">
      <TravelerProfile v-for="trips in travelTrips" :key="'trips' + trips.id" :trips="trips"/>
    </div>
  </div>
</template>

<script>
import TravelerProfile from "../views/TravelerProfile.vue";
export default {
  components: {
    TravelerProfile
  },
  props: ["travelTrips"]
};
</script>

<style scoped>
.cards {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-around;
}
</style>
