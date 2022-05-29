<template>
  <div class="destinations">
    <h1><span>01</span> PICK YOUR DESTINATION</h1>
    <div class="destination-txt">
      <button
        v-for="(item, index) in data"
        :class="{ active: index === activeId }"
        :key="item.name"
        v-on:click="
          activeId = data.indexOf(item);
          changeActive(index);
        "
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
      isActive: null,
    };
  },
  methods: {
    changeActive(index) {
      this.isActive = this.isActive === index ? null : index;
    },
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
  width: 42%;
  margin-right: 0;
}
button {
  background-color: rgba(255, 255, 255, 0);
  color: #d0d6f9;
  border: none;
  padding: 2rem 1.5rem 1.5rem 0;
  margin-bottom: 0;
}
button h2:hover {
  border-bottom: solid 0.12rem rgba(255, 255, 255, 0.5);
}
.active h2,
.active h2:hover {
  border-bottom: solid 0.15rem white;
}
h2 {
  font-family: "Barlow Condensed", sans-serif;
  font-size: 1.2rem;
  font-weight: 400;
  letter-spacing: 2.7px;
  padding-bottom: 0.5rem;
}
</style>
