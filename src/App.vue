<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link>|
      <router-link to="/about">About</router-link>|
      <router-link to="/traveler">Travelers</router-link>
    </div>
    <router-view
      :travelPassport="travelPassport"
      :travelTrips="travelTrips"
      :travelCountry="travelCountry"
      :travelData="travelData"
    />
  </div>
</template>
<script>
export default {
  data() {
    return {
      travelPassport: null,
      travelTrips: null,
      travelCountry: null,
      travelData: null
    };
  },
  methods: {
    getTravelers() {
      fetch("http://localhost:3001/traveler")
        .then(resp => resp.json())
        .then(resp => (this.travelPassport = resp));
    },
    getTrips() {
      fetch("http://localhost:3001/trips")
        .then(resp => resp.json())
        .then(resp => (this.travelTrips = resp));
    },
    getCountries() {
      fetch("http://localhost:3001/countries")
        .then(resp => resp.json())
        .then(resp => (this.travelCountry = resp));
    },
    updateDescription() {
      patch("http://localhost:3001/trips")
        .then()
    }
    // getJoinedData() {
    //   fetch("http://localhost:3001/travelerTrips/:id")
    //     .then(resp => resp.json())
    //     .then(resp => (this.travelData = resp));
    // }
  },
  mounted() {
    this.getTravelers();
    this.getTrips();
    this.getCountries();
    // this.getJoinedData();
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
  background-color: lightpink;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: salmon;
}
</style>
