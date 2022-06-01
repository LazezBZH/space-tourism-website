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
  height: 10rem;
}
h3 {
  font-family: "Bellefair", serif;
  font-size: 6.2rem;
  font-weight: 200;
  margin-top: 0;
  line-height: 7rem;
}
.description {
  width: 90%;
  font-family: "Barlow", sans-serif;
  font-size: 1.1rem;
  font-weight: 300;
  margin: 2rem auto 2rem 0;
  color: #d0d6f9;
  line-height: 1.8rem;
}
.under-description {
  width: 90%;
  display: flex;
  justify-content: left;
  margin-top: 3.5rem;
  margin-left: 0;
  padding-top: 1.5rem;
  border-top: 0.05rem solid rgba(151, 151, 151, 1);
}
.grey-p {
  color: #d0d6f9;
  font-family: "Barlow condensed", sans-serif;
  letter-spacing: 2.36px;
  font-size: 1rem;
}
.white-p {
  font-family: "Bellefair", serif;
  font-size: 1.8rem;
}
.distance,
.travel {
  margin: 0;
}
.distance {
  margin-right: 4rem;
}
.image img {
  width: 100%;
}

@media screen and (min-width: 500px) and (max-width: 770px) {
  .destination {
    margin: auto;
    text-align: center;
  }
  .distance,
  .travel {
    margin: auto;
  }
  h3 {
    font-size: 5rem;
  }
  .description {
    width: 92.5%;
    font-size: 0.9rem;
  }
  .grey-p {
    font-size: 0.9rem;
  }
  .white-p {
    font-size: 1.5rem;
  }
}
</style>
