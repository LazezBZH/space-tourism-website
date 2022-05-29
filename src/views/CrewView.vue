<template>
  <div class="crews">
    <h1><span>02</span> MEET YOUR CREW</h1>
    <div class="crew-txt">
      <div class="crew-all">
        <OneCrew :i="activeId"></OneCrew>

        <button
          v-for="(item, index) in data"
          :class="{ active: index === activeId }"
          :key="item.name"
          v-on:click="
            activeId = data.indexOf(item);
            changeActive(index);
          "
        ></button>
      </div>
    </div>
  </div>
</template>
<script>
import json from "../data.json";
let data = json.crew;

console.log(data);

import OneCrew from "@/components/OneCrew.vue";

export default {
  name: "CrewView",
  components: { OneCrew },
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
.crews {
  max-width: 1440px;
  padding-top: 17%;
  width: 100%;
  height: 100vh;
  background-image: url("@/assets/crew/background-crew-desktop.jpg");
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
.crew-txt {
  width: 57%;
  height: 60vh;
  margin-left: 0;
  position: relative;
}
.crew-all {
  width: 75%;
  position: absolute;
  bottom: 0;
  right: 0;
  padding-bottom: 2rem;
}
button {
  width: 0.7rem;
  height: 0.7rem;
  background-color: rgba(255, 255, 255, 0.174);
  border: none;
  padding: 0;
  margin: 3rem 2rem 0 0;
  border-radius: 50%;
}
button:hover {
  background-color: rgba(255, 255, 255, 0.5);
}
.active,
.active:hover {
  background-color: rgba(255, 255, 255);
}
h2 {
  font-family: "Barlow Condensed", sans-serif;
  font-size: 1.5rem;
  font-weight: 400;
  letter-spacing: 2.7px;
}
</style>
