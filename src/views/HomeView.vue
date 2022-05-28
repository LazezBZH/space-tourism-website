<template>
  <div class="home">
    <HomeText />
    <HomeButton />
  </div>
</template>

<script>
// @ is an alias to /src
import HomeText from "@/components/HomeText.vue";
import HomeButton from "@/components/HomeButton.vue";

export default {
  name: "HomeView",
  components: {
    HomeText,
    HomeButton,
  },
};
</script>
<style scoped>
.home {
  max-width: 1440px;

  padding-top: 17%;
  width: 100%;
  height: 100vh;
  background-image: url("@/assets/home/background-home-desktop.jpg");
  background-size: auto;
  background-repeat: no-repeat;
  background-position: top right;
}
</style>
