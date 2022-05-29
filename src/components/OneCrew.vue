<template>
  <div :class="data[i].name" class="crew">
    <h3 class="role">{{ data[i].role.toUpperCase() }}</h3>
    <h4 class="name">{{ data[i].name.toUpperCase() }}</h4>
    <p class="bio">
      {{ data[i].bio }}
    </p>
  </div>
</template>

<script>
import json from "../data.json";
let data = json.crew;
console.log(data);

export default {
  name: "OneCrew",
  props: {
    i: {},
  },
  data() {
    return {
      data,
    };
  },
  methods: {},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.crew {
  color: white;
  width: 80%;
  margin-left: 0;
  margin-top: 0;
}
.image {
  width: 10rem;
}
h3 {
  font-family: "Noto Serif", serif;
  font-size: 1.5rem;
  font-weight: 400;
  color: rgba(255, 255, 255, 0.5);
}
h4 {
  font-family: "Noto Serif", serif;
  font-size: 2.62rem;
  font-weight: 400;
  margin: 1.3rem auto;
}
.bio {
  font-family: "Barlow", sans-serif;
  font-size: 1.2rem;
  margin: 1rem auto 2rem auto;
  padding-right: 2.1rem;
  color: rgba(208, 214, 249, 0.9);
  line-height: 1.8rem;
}
</style>
