<template>
  <div>
    <h1></h1>
    <div class="cards">
      <IndividualTraveler
        v-for="traveler in travelPassport"
        :key="'traveler' + traveler.id"
        :traveler="traveler"
      />
    </div>
  </div>
</template>

<script>
import IndividualTraveler from "../components/IndividualTraveler.vue";
import TravelerProfile from "../views/TravelerProfile.vue";

export default {
  components: {
    IndividualTraveler
  },
  props: ["travelPassport"]
};
</script>

<style scoped>
.cards {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-around;
}
</style>
