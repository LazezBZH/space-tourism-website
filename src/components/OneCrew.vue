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
  width: 100%;
  margin-left: 0;
  margin-top: 0;
}

h3 {
  font-family: "Bellefair", serif;
  font-size: 1.9rem;
  font-weight: 400;
  color: rgba(255, 255, 255, 0.5);
}
h4 {
  font-family: "Bellefair", serif;
  font-size: 3.3rem;
  font-weight: 400;
  margin: 1.3rem 0;
}
.bio {
  width: 71%;
  font-family: "Barlow", sans-serif;
  font-size: 1.1rem;
  font-weight: 300;
  margin: 1rem auto 2.5rem 0;
  padding-right: 1.5rem;
  color: #d0d6f9;
  line-height: 1.5rem;
}
</style>
