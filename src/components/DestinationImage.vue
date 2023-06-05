<template>
  <img :src="data[i].images.photo" />
</template>

<script>
import json from "../data.json";
let data = json.destinations;

export default {
  name: "DestinationImage",
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
