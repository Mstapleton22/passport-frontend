<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link>|
      <router-link to="/about">About</router-link>|
      <router-link to="/traveler">Travelers</router-link>
    </div>
    <router-view :travelPassport="travelPassport"/>
  </div>
</template>
<script>
export default {
  data() {
    return {
      travelPassport: null
    };
  },
  methods: {
    getTravelers() {
      fetch("http://localhost:3001/traveler")
        .then(resp => resp.json())
        .then(resp => (this.travelPassport = resp));
    }
  },
  mounted() {
    this.getTravelers();
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
