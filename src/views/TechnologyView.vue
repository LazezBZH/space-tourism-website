<template>
  <div class="technologies">
    <h1><span>02</span> SPACE LAUNCH 101</h1>
    <div class="technology-details">
      <div class="technology-txt">
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
      <div class="technology-image">
        <TechnologyImage :i="activeId"></TechnologyImage>
      </div>
    </div>
  </div>
</template>
<script>
import json from "../data.json";
let data = json.technology;

console.log(data);
import OneTechnology from "../components/OneTechnology";
import TechnologyImage from "../components/TechnologyImage.vue";

export default {
  name: "TechnologyView",
  components: { OneTechnology, TechnologyImage },
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
  padding-top: 15%;
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
  margin-bottom: 2%;
}
h1 span {
  padding-right: 2rem;
  color: rgba(255, 255, 255, 0.4);
  font-weight: 700;
}
.technology-details {
  width: 100%;

  margin-left: 0;
  position: relative;
  display: flex;
}
.technology-txt {
  width: 45.5%;
  height: 60%;
  display: flex;
  padding-top: 5rem;
}
.technology-image {
  display: flex;
  align-items: center;
  margin: 0;
}
.technology-image img {
  height: 527px;
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
  background-color: rgba(255, 255, 255, 0);
  border: solid 0.12rem rgba(255, 255, 255, 0.174);
  color: white;
  border-radius: 50%;
  font-size: 2rem;
  margin-bottom: 1rem;
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

@media screen and (min-width: 850px) and (max-width: 1020px) {
  .technology-image {
    display: flex;
    align-items: center;
    margin: 0;
  }
  .technology-image img {
    height: 400px;
  }
  .btn {
    padding-right: 3rem;
  }
  button {
    margin-bottom: 3rem;
  }
}
@media screen and (min-width: 1003px) and (max-width: 1383px) {
  button {
    margin-bottom: 3rem;
  }
}
@media screen and (min-width: 850px) and (max-width: 1002px) {
  button {
    margin-bottom: 5rem;
  }
}
</style>
