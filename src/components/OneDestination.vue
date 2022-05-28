<template>
  <div :class="data[i].name" class="destination">
    <h3>{{ data[i].name.toUpperCase() }}</h3>
    <p class="description">{{ data[i].description }}</p>
    <div class="under-description">
      <div class="distance">
        <p class="grey-p">AVG. DISTANCE</p>
        <p class="white-p">{{ data[i].distance.toUpperCase() }}</p>
      </div>
      <div class="travel">
        <p class="grey-p">EST. TRAVEL TIME</p>
        <p class="white-p">{{ data[i].travel.toUpperCase() }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import json from "../data.json";
let data = json.destinations;
console.log(data);

export default {
  name: "OneDestination",
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
.destination {
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
  font-size: 8rem;
  font-weight: 200;
  margin-top: 0;
  line-height: 7rem;
}
.description {
  font-family: "Barlow", sans-serif;
  font-size: 1.5rem;
  margin: 2rem auto;
  color: #d0d6f9;
}
.under-description {
  display: flex;
  justify-content: left;
  margin-top: 5rem;
}
.grey-p {
  color: #d0d6f9;
  font-family: "Barlow condensed", sans-serif;
  letter-spacing: 2.36px;
  font-size: 1.5rem;
}
.white-p {
  font-family: "Noto Serif", serif;
  font-size: 2.5rem;
}
.distance,
.travel {
  margin: 0;
}
.distance {
  margin-right: 4rem;
}
</style>
