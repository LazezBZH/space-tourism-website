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

  width: 100%;
  height: 100vh;
  background-image: url("@/assets/crew/background-crew-desktop.jpg");
  background-size: auto;
  background-repeat: no-repeat;
  background-position: top right;
  margin: 0;
}
h1 {
  color: white;
  font-family: "Barlow Condensed", sans-serif;
  font-size: 1.7rem;
  letter-spacing: 4.72px;
  font-weight: 400;
  margin-left: 10rem;
  position: absolute;
  top: 12rem;
}
h1 span {
  padding-right: 2rem;
  color: rgba(255, 255, 255, 0.4);
  font-weight: 700;
}
.crew-details {
  width: 100%;
  height: auto;
  margin: 0;
  position: absolute;
  top: 15rem;
  bottom: -5rem;
  display: flex;
  flex-direction: row;
  justify-content: stretch;
}
.crew-txt {
  width: 43%;
  margin-top: 15%;
  margin-left: 10rem;
}
.crew-image {
  height: auto;
  position: absolute;
  right: 0;

  bottom: -1.2rem;

  margin: -5.3% 7rem auto auto;
  vertical-align: baseline;
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

@media screen and (min-width: 851px) and (max-width: 1222px) {
  .crew-image {
    height: 720px;
    display: flex;
    position: absolute;
    right: 0;
    bottom: -10rem;
    margin-right: 1rem;
  }

  .crew-txt {
    margin-left: 5rem;
  }
}

@media screen and (min-width: 601px) and (max-width: 850px) {
  .crew-details {
    display: flex;
    flex-direction: column;
  }
  .crew-image,
  .crew-txt {
    position: initial;
  }
  .crews {
    height: 100vh;
    background-image: url("@/assets/crew/background-crew-tablet.jpg");
    background-size: cover;
    padding-bottom: 50rem;
  }
  h1 {
    font-size: 1.2rem;
    margin-left: 2rem;
    margin-top: 2rem;
    margin-bottom: 2%;
  }
  .crew-txt {
    width: 90%;
    margin: 2rem auto;
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

@media screen and (max-width: 600px) {
  .crew-details {
    display: flex;
    flex-direction: column-reverse;
  }
  .crew-image,
  .crew-txt {
    position: initial;
  }
  .crews {
    height: 110vh;
    background-image: url("@/assets/crew/background-crew-mobile.jpg");
    background-size: cover;
    padding-bottom: 0;
    margin: auto;
  }
  h1 {
    width: 100%;
    font-size: 1.3rem;
    text-align: center;
    margin: -5rem auto auto auto;
  }
  .crew-txt {
    width: 90%;
    margin: 2rem auto;
    display: flex;
    flex-direction: column-reverse;
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
    height: 550px;
  }
  button {
    margin-top: 0;
  }
}
</style>
