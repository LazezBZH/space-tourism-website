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
  height: 83%;
  background-image: url("@/assets/home/background-home-desktop.jpg");
  background-size: 100%;
  background-repeat: no-repeat;
  background-position: top right;
}

@media screen and (min-width: 401px) and (max-width: 830px) {
  .home {
    background-image: url("@/assets/home/background-home-tablet.jpg");
    background-size: 130%;
  }
}
@media screen and (min-width: 631px) and (max-width: 1000px) {
  .home {
    margin: auto;
    background-size: 110% 100%;
  }
}
@media screen and (max-width: 400px) {
  .home {
    margin: 0 auto;
    background-image: url("@/assets/home/background-home-mobile.jpg");
    background-size: 130%;
    background-repeat: no-repeat;
    background-position: -10% right;
  }
}
</style>
