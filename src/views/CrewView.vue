<template>
  <div class="crews">
    <h1><span>02</span> MEET YOUR CREW</h1>
    <div class="crew-details">
      <div class="crew-txt">
        <OneCrew :i="activeId"></OneCrew>

        <div class="crew-btn">
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
      <div class="crew-image">
        <CrewImage :i="activeId"></CrewImage>
      </div>
    </div>
  </div>
</template>
<script>
import json from "../data.json";
let data = json.crew;

console.log(data);

import OneCrew from "@/components/OneCrew.vue";
import CrewImage from "@/components/CrewImage.vue";

export default {
  name: "CrewView",
  components: { OneCrew, CrewImage },
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
  padding-top: 15%;
  width: 100%;
  height: 900px;
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
.crew-details {
  width: 100%;
  height: 100%;
  margin: 0;
  position: relative;
  display: flex;
  flex-direction: row;
}
.crew-txt {
  width: 43%;
  margin-top: 15%;
  margin-left: 10rem;
  position: absolute;
  top: 0;
}
.crew-image {
  height: 720px;
  display: flex;
  position: absolute;
  right: 10%;
  bottom: 24.5%;
}
.crew-image img {
  width: 95%;
  height: 95%;
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

@media screen and (min-width: 851px) and (max-width: 1210px) {
  .crew-image {
    height: 720px;
    display: flex;
    position: absolute;
    right: 5%;
    bottom: 10%;
  }
  .crew-image img {
    width: 80%;
    height: 80%;
  }
  .crew-txt {
    margin-left: 5rem;
  }
}

@media screen and (min-width: 500px) and (max-width: 850px) {
  .crew-details {
    display: flex;
    flex-direction: column;
  }
  .crew-image,
  .crew-txt {
    position: initial;
  }
  .crews {
    height: 1024px;
    background-image: url("@/assets/crew/background-crew-tablet.jpg");
    background-size: 100%;
  }
  h1 {
    font-size: 1.2rem;
    margin-left: 2rem;
    margin-top: 2rem;
    margin-bottom: 2%;
  }
  .crew-txt {
    width: 90%;
    margin: auto;
  }
  .crew-image {
    width: auto;
    max-height: 572px;
    margin: auto;
    display: block;
    text-align: center;
  }
  .crew-image img {
    width: auto;
    max-height: 500px;
    position: absolute;
    bottom: 18%;
    left: 25%;
  }
  .crew-btn {
    width: 40%;
    display: flex;
    justify-content: center;
    margin: auto;
  }
}
</style>
