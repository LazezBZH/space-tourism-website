<template>
  <div class="img"><img :src="data[i].images.photo" /></div>
</template>

<script>
import json from "../data.json";
let data = json.crew;

export default {
  name: "CrewImage",
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
.img {
  height: auto;
  display: block;
  flex-wrap: nowrap;
  -webkit-box-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  align-items: center;
  margin: 0;
}
.img img {
  height: auto;
  vertical-align: baseline;
}

@media screen and (min-width: 851px) and (max-width: 1222px) {
  .img {
    height: 70%;
    display: block;
    flex-wrap: nowrap;
    -webkit-box-pack: center;
    justify-content: center;
    -webkit-box-align: center;
    align-items: center;
    margin: 0;
  }
  .img img {
    height: 100%;
    vertical-align: baseline;
  }
}
@media screen and (max-width: 600px) {
  .img img {
    margin-top: 5rem;
    height: 22rem;
  }
}
@media screen and (max-width: 350px) {
  .img img {
    margin-top: 5rem;
    height: 18rem;
  }
}
</style>
