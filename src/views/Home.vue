<template>
  <div class="home">
    <div class="content">
      <div class="text-wrapper">
        <h1>Passportal</h1>
        <h6>Everything you need to remember the good times.</h6>
      </div>
      <div class="text-wrapper1">
        <h4>Storage
          <br>Blog - Document - Share with friends!
        </h4>
      </div>
      <img
        src="https://openclipart.org/image/2400px/svg_to_png/253812/Low-Poly-Shattered-World-Map-No-Background.png"
        alt="the world"
      >
    </div>
  </div>
</template>

<script>
export default {
  name: "home",
  components: {}
};
</script>

<style scoped>
img {
  z-index: -1;
  max-width: 100vw;
  max-height: 100vh;
  position: absolute;
  left: 0%;
  top: 0%;
  background-size: cover;
  background-position: center;
  background-color: lightcyan;
}

.home {
  position: absolute;
}

.content {
  position: relative;
  z-index: 2;
  display: flex;
  flex-direction: column;
  align-content: center;
  justify-content: center;
  left: 0%;
  top: 0%;
}

.text-wrapper {
  display: flex;
  flex-direction: column;
  width: 30vh;
  margin-top: 320px;
  margin-left: 30px;
  background-color: lightpink;
  border: 3px solid green;
  padding: 5px;
  border-radius: 25px;
}

.text-wrapper1 {
  display: flex;
  flex-direction: column;
  margin-top: -400px;
  margin-left: 500px;
  width: 10vw;
  height: 20vh;
  background-color: lightpink;
  border: 3px solid green;
  padding: 5px;
  border-radius: 25px;
}

</style>

