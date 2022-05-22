<template>
  <div class="home-btn">
    <img alt="logo" src="@/assets/button.svg" />
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
  font-family: "Noto Serif", serif;
  font-size: 2rem;
  border: none;
  position: absolute;
  bottom: 34%;
  left: 67%;
}
.home-btn img {
  border: solid 2rem rgba(0, 0, 0, 0);
  border-radius: 50%;
}
.home-btn img:hover {
  border: solid 2rem #0b0d17;
  border-radius: 50%;
}
</style>
