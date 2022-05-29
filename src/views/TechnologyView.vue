<template>
  <div class="technologies">
    <h1><span>02</span> SPACE LAUNCH 101</h1>
    <div class="technology-txt">
      <div class="technology-all">
        <div class="btn">
          <button
            v-for="(item, index) in data"
            :class="{ active: index === activeId }"
            :key="item.name"
            :id="data.indexOf(item)"
            v-on:click="
              activeId = data.indexOf(item);
              changeActive(index);
            "
          >
            {{ data.indexOf(item) + 1 }}
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
  height: 90%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding-right: 5rem;
}
button {
  width: 5rem;
  height: 5rem;
  background-color: rgba(255, 255, 255, 0);
  border: solid 0.12rem rgba(255, 255, 255, 0.174);
  color: white;
  padding: 0;
  border-radius: 50%;
  font-size: 2rem;
}
button:hover {
  border: solid 0.12rem rgba(255, 255, 255, 0.6);
}
.active,
.active:hover {
  color: black;
  background-color: white;
}
h2 {
  font-family: "Barlow Condensed", sans-serif;
  font-size: 1.5rem;
  font-weight: 400;
  letter-spacing: 2.7px;
}
</style>
