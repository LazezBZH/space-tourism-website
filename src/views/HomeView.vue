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
  background-size: 100%;
  background-repeat: no-repeat;
  background-position: top right;
}

@media screen and (min-width: 531px) and (max-width: 999px) {
  .home {
    background-image: url("@/assets/home/background-home-tablet.jpg");
    background-size: 100%;
  }
}
@media screen and (min-width: 601px) and (max-width: 849px) {
  .home {
    margin: 0 auto;
  }
}
@media screen and (max-width: 530px) {
  .home {
    margin: 0 auto;
    background-image: url("@/assets/home/background-home-mobile.jpg");
    background-size: 100%;
    background-repeat: no-repeat;
    background-position: top right;
  }
}
</style>
