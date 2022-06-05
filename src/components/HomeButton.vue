<template>
  <div class="home-btn">
    <img alt="logo" src="/assets/button.svg" />
  </div>
</template>

<script>
export default {
  name: "HomeButton",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.home-btn {
  max-height: 100vh;
  font-family: "Noto Serif", serif;
  font-size: 2rem;
  border: none;
  position: relative;
}
.home-btn img {
  position: absolute;
  bottom: -2rem;
  right: 7%;

  border: solid 3.5rem rgba(0, 0, 0, 0);
  border-radius: 50%;
}
.home-btn img:hover {
  border: solid 3.5rem rgba(151, 151, 151, 0.4);
  border-radius: 50%;
}

@media screen and (min-width: 850px) and (max-width: 1040px) {
  .home-btn img {
    position: absolute;
    bottom: -3rem;
    right: 2%;
  }
}

@media screen and (min-width: 631px) and (max-width: 849px) {
  .home-btn img {
    width: 30%;
    position: absolute;
    bottom: 0;
    top: 0;
    left: 0;
    right: 0;
  }
}
@media screen and (min-width: 601px) and (max-width: 630px) {
  .home-btn img {
    width: 30%;
    position: absolute;
    bottom: 0;
    top: -5rem;
    left: 0;
    right: 0;
  }
}
@media screen and (max-width: 600px) {
  .home-btn img {
    width: 40%;
    position: absolute;
    bottom: 0;
    top: -2rem;
    left: 0;
    right: 0;
  }
}
</style>
