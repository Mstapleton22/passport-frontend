<template>
  <div class="passport">
    <div class="trips">
      <img src="../assets/passportBackground.png" alt="passport">
      <div class="col1">
        <p>Name: {{traveler.first_name}} {{traveler.last_name}}</p>
      </div>
      <!-- <div class="col2"></div> -->
      <div class="col2">
        <p>Country Visited: {{traveler.country_name}}</p>
        <p>Country Language: {{country.language}}</p>
        <p>Trip Memories:
          <br>
          {{trips.description}}
        </p>
      </div>
      <button v-on:click="trips.description + 1">Next</button>
      <!-- <router-link class="link" v-bind:to="{ path: `/profile/${traveler.id}` }"> -->
      <!-- <div class="edit">
        Description:
        <input
          type="text"
          v-model="trips.description"
          :disabled="!isEditing"
          :class="{view: !isEditing}"
        >
      </div>
      <button v-on:click="isEditing = !isEditing" v-if="!isEditing">Edit</button>
      <button v-on:click="save" v-else-if="isEditing">Save</button>
      <button v-if="isEditing" v-on:click="isEditing = false">Cancel</button>-->
      <!-- </router-link> -->
    </div>
  </div>
</template>

<script>
export default {
  data: {
    isEditing: false,
    trips: {
      description: ""
    }
  },
  props: ["travelTrips", "travelCountry", "travelPassport"],

  computed: {
    traveler: function() {
      return this.travelPassport.filter(traveler => {
        let travelerId = +this.$route.params.id;
        return travelerId === traveler.id;
      })[0];
    },
    trips: function() {
      return this.travelTrips.filter(trip => {
        let tripId = +this.$route.params.id;
        return tripId === trip.id;
      })[0];
    },
    country: function() {
      return this.travelCountry.filter(country => {
        let countryId = +this.$route.params.id;
        return countryId === country.id;
      })[0];
    }
    // save() {
    //   this.trips.description = this.$refs["description"].value;
    //   this.isEditing = !this.isEditing;
    // }
  }
};
</script>
<style scoped>
img {
  z-index: -1;
  max-width: 100vw;
  max-height: 100vh;
  position: absolute;
  left: 15%;
  top: 20%;
  background-size: cover;
  background-position: center;
}
/* .passport {
  position: absolute; */
.trips {
  display: grid;
  grid-template-columns: repeat(2, 0.45fr);
  font-family: "Inconsolata", monospace;
  grid-column-gap: 150px;
}
/* .view {
  border-color: transparent;
  background-color: initial;
  color: initial;
} */
.col1 {
  display: flex;
  flex-direction: column;
  /* justify-content: center; */
  margin-top: 170px;
  margin-left: 150px;
  padding-left: 20%;
  font-size: 2em;
}
.edit {
  width: 100%;
  height: 100%;
}
.col2 {
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin-top: 100px;
  padding: 15%;
  text-align: start;
  font-size: 1.4em;
}
</style>
