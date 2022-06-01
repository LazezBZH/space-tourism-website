<template>
  <img :src="data[i].images.landscape" />
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
<style scoped></style>
