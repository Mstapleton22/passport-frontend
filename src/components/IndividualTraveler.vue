<template>
  <router-link class="link" v-bind:to="{ path: `/profile/${traveler.id}` }">
    <div class="travelerCard">
      <div class="col1">
        <img :src="traveler.picture" alt="passport image">
      </div>
      <div class="col2">
        <p>Name: {{traveler.first_name}} {{traveler.last_name}}</p>
        <p>Nationality:
          <br>
          {{traveler.nationality}}
        </p>
        <img class="stamp" src="../assets/passportStamp.png" alt="passportstamp">
      </div>
    </div>
  </router-link>
</template>

<script>
export default {
  props: ["traveler"]
};
</script>

<style scoped>
.travelerCard {
  background-color: beige;
  color: black;
  max-width: 20vw;
  max-height: 100%;
  padding-right: 140px;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  font-family: "Inconsolata", monospace;
  border: 10px solid navy;
}
img {
  max-width: 25vw;
  max-height: 25vh;
  margin: 20px;
  padding-top: 20px;
}
.stamp {
  max-width: 15vw;
  max-height: 15vh;
  margin-left: -20px;
  margin-top: -60px;
  z-index: 1;
  -webkit-transform: rotate(50deg);
  -moz-transform: rotate(50deg);
  -o-transform: rotate(50deg);
  -ms-transform: rotate(50deg);
  transform: rotate(50deg);
}
.link {
  text-decoration: none;
}

.col1 {
  /* min-height: 100vh; */
}

.col2 {
}
</style>