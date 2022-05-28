<template>
  <div class="destinations">
    <h1><span>01</span> PICK YOUR DESTINATION</h1>
    <div class="destination-txt">
      <button
        v-for="item in data"
        :key="item.name"
        v-on:click="activeId = data.indexOf(item)"
      >
        <h2>{{ item.name.toUpperCase() }}</h2>
      </button>

      <OneDestination :i="activeId"></OneDestination>
    </div>
  </div>
</template>
<script>
import json from "../data.json";
let data = json.destinations;

console.log(data);

import OneDestination from "@/components/OneDestination.vue";

export default {
  name: "DestinationView",
  components: { OneDestination },
  data() {
    return {
      data,
      activeId: 0,
    };
  },
};
</script>
<style scoped>
.destinations {
  max-width: 1440px;
  padding-top: 17%;
  width: 100%;
  height: 100vh;
  background-image: url("@/assets/destination/background-destination-desktop.jpg");
  background-size: auto;
  background-repeat: no-repeat;
  background-position: top right;
}
h1 {
  color: white;
  font-family: "Barlow Condensed", sans-serif;
  font-size: 1.7rem;
  letter-spacing: 4.72px;
  font-weight: 400;
  margin-left: 10rem;
}
h1 span {
  padding-right: 2rem;
  color: rgba(255, 255, 255, 0.4);
  font-weight: 700;
}
.destination-txt {
  width: 50%;
  margin-right: 0;
}
button {
  background-color: rgba(255, 255, 255, 0);
  color: #d0d6f9;
  border: none;
  padding: 2rem 2rem 2rem 0;
  margin-bottom: 0;
}
h2 {
  font-family: "Barlow Condensed", sans-serif;
  font-size: 1.5rem;
  font-weight: 400;
  letter-spacing: 2.7px;
}
</style>
