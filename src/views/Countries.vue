<template>
  <div>
    <div class="cards">
      <TravelerProfile v-for="country in travelCountry" :key="'country' + country.id" :country="country"/>
    </div>
  </div>
</template>

<script>
import TravelerProfile from "../components/TravelerProfile.vue";
export default {
  components: {
    TravelerProfile
  },
  props: ["travelCountry"]
};
</script>

<style scoped>
.cards {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-around;
}
</style>