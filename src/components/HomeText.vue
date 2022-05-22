<template>
  <div class="home-txt">
    <h2>SO, YOU WANT TO TRAVEL TO</h2>
    <h1>SPACE</h1>

    <p>
      Let’s face it; if you want to go to space, you might as well genuinely go
      to outer space and not hover kind of on the edge of it. Well sit back, and
      relax because we’ll give you a truly out of this world experience!
    </p>
  </div>
</template>

<script>
export default {
  name: "HomeText",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.home-txt {
  width: 30%;
  margin-left: 10%;
  margin-top: 10%;
}
h2 {
  color: #d0d6f9;
  width: auto;
  font-family: "Barlow Condensed", sans-serif;
  font-size: 2.4rem;
  font-weight: 400;
}
h1 {
  font-family: "Noto Serif", serif;
  color: white;
  font-size: 9rem;
  font-weight: 400;
  margin: 0.1rem auto 1.1rem auto;
}
p {
  font-family: "Barlow", sans-serif;
  color: #d0d6f9;
  text-align: left;
  font-size: 1.15rem;
  line-height: 1.9rem;
}
</style>
