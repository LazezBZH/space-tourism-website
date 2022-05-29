<template>
  <div class="technologies">
    <h1><span>02</span> SPACE LAUNCH 101</h1>
    <div class="technology-txt">
      <div class="technology-all">
        <div class="btn">
          <button
            v-for="item in data"
            :key="item.name"
            v-on:click="activeId = data.indexOf(item)"
          >
            {{ data.indexOf(item) }}
          </button>
        </div>
        <OneTechnology :i="activeId"></OneTechnology>
      </div>
    </div>
  </div>
</template>
<script>
import json from "../data.json";
let data = json.technology;

console.log(data);
import OneTechnology from "../components/OneTechnology";
export default {
  name: "TechnologyView",
  components: { OneTechnology },
  data() {
    return {
      data,
      activeId: 0,
    };
  },
};
</script>
<style scoped>
.technologies {
  max-width: 1440px;
  padding-top: 17%;
  width: 100%;
  height: 100vh;
  background-image: url("@/assets/technology/background-technology-desktop.jpg");
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
.technology-txt {
  width: 57%;
  height: 60vh;
  margin-left: 0;
  position: relative;
}
.technology-all {
  width: 79.7%;
  height: 60%;
  position: absolute;
  bottom: 22%;
  right: 0;

  display: flex;
}
.btn {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding-right: 5rem;
}
button {
  width: 5rem;
  height: 5rem;
  background-color: white;
  color: black;
  border: none;
  padding: 0;
  border-radius: 50%;
  font-size: 2rem;
}
h2 {
  font-family: "Barlow Condensed", sans-serif;
  font-size: 1.5rem;
  font-weight: 400;
  letter-spacing: 2.7px;
}
</style>
