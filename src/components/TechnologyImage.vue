<template>
  <div class="img"><img :src="data[i].images.portrait" /></div>
</template>

<script>
import json from "../data.json";
let data = json.technology;

export default {
  name: "TechnologyImage",
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
  margin-top: -2rem;
  padding-bottom: 6rem;
}
</style>
