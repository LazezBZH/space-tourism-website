<template>
  <div class="technologies">
    <h1><span>02</span> SPACE LAUNCH 101</h1>
    <div class="technology-details">
      <div class="technology-txt">
        <div class="technology-btn">
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
      <div class="technology-image-portrait">
        <TechnologyImage :i="activeId"></TechnologyImage>
      </div>
      <div class="technology-image-landscape">
        <TechnologyLandscapeImage :i="activeId"></TechnologyLandscapeImage>
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
import TechnologyLandscapeImage from "../components/TechnologyLandscapeImage.vue";

export default {
  name: "TechnologyView",
  components: { OneTechnology, TechnologyImage, TechnologyLandscapeImage },
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

  background-image: url("@/assets/technology/background-technology-desktop.jpg");
  background-size: cover;
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
.technology-image-portrait {
  display: flex;
  align-items: center;
  margin: 0;
}
.technology-image-portrait img {
  height: 527px;
}
.technology-image-landscape {
  display: none;
}
.technology-btn {
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
  .technology-image-portrait {
    display: flex;
    align-items: center;
    margin: 0;
  }
  .technology-image-portrait img {
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
@media screen and (min-width: 851px) and (max-width: 1002px) {
  button {
    margin-bottom: 5rem;
  }
}

@media screen and (min-width: 500px) and (max-width: 849px) {
  h1 {
    font-size: 1.2rem;
    margin-left: 2rem;
    margin-top: 2rem;
    margin-bottom: 2%;
  }
  .technology-details {
    display: flex;
    flex-direction: column-reverse;
  }
  .technology-image-landscape {
    display: block;
    width: 100%;
  }
  .technology-image-landscape img {
    width: 100%;
  }
  .technology-image-portrait {
    display: none;
  }
  .technology-txt {
    width: 100%;
    display: block;
    padding-top: 3rem;

    margin: auto;
  }
  .technology-btn {
    width: 30%;
    display: flex;
    flex-direction: row;
    justify-content: center;
    margin: auto;
    padding: 0;
  }

  button {
    width: 3rem;
    height: 3rem;
    background-color: rgba(255, 255, 255, 0);
    border: solid 0.12rem rgba(255, 255, 255, 0.174);
    color: white;
    border-radius: 50%;
    font-size: 2rem;
    margin-bottom: 2rem;
  }
  .technologies {
    background-image: url("@/assets/technology/background-technology-tablet.jpg");
    background-size: cover;
  }
}
@media screen and (max-width: 600px) {
  .technology {
    background-image: url("@/assets/technology/background-technology-mobile.jpg");
    background-size: cover;
    background-repeat: no-repeat;
    background-position: top right;
    margin: auto;
  }
  h1 {
    font-size: 1rem;
    margin: 5% auto auto 4rem;
  }
  h1 span {
    padding-right: 1rem;
  }
  .technology-details {
    display: flex;
    flex-direction: column-reverse;
  }
  .technology-image-landscape {
    display: block;
    width: 100%;
  }
  .technology-image-landscape img {
    width: 100%;
  }
  .technology-image-portrait {
    display: none;
  }
  .technology-txt {
    width: 99%;
    display: block;
    padding-top: 3rem;
    margin: auto;
    text-align: center;
  }
  .technology-btn {
    width: 60%;
    display: flex;
    flex-direction: row;
    justify-content: center;
    margin: auto;
    padding: 0;
  }

  button {
    width: 1.2rem;
    height: 1.8rem;
    background-color: rgba(255, 255, 255, 0);
    border: solid 0.12rem rgba(255, 255, 255, 0.174);
    color: white;
    border-radius: 50%;
    font-size: 1.5rem;
    margin-bottom: 2rem;
  }
}
</style>
