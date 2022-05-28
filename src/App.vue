<template>
  <nav>
    <img alt="logo" src="./assets/shared/logo.svg" />
    <div class="trait"></div>
    <div class="links">
      <router-link class="link link_1" to="/"
        ><span class="bold">00</span> HOME</router-link
      >
      <router-link class="link link_2" to="/destination"
        ><span class="bold">01</span> DESTINATION</router-link
      >
      <router-link class="link link_3" to="/crew"
        ><span class="bold">02</span> CREW</router-link
      >
      <router-link class="link link_4" to="/technology"
        ><span class="bold">03</span> TECHNOLOGY</router-link
      >
    </div>
  </nav>
  <router-view />
</template>

<style>
* {
  margin: 0.2rem auto;
}
#app {
  position: relative;
  max-width: 1440px;
}

nav {
  font-family: "Barlow Condensed", sans-serif;
  font-size: 1rem;
  font-weight: 400;
  letter-spacing: 2.7px;
  width: 96.18%;
  height: 10.66vh;
  position: absolute;
  left: 3.82%;
  top: 0;
  display: flex;
  justify-content: space-between;
  margin: 2% auto auto 0;
}
nav .bold {
  font-weight: 700;
}
nav img {
  margin: auto 0;
}

nav a {
  color: white;
  margin: auto 2rem;
  text-decoration: none;
}

nav a.router-link-exact-active,
nav a.router-link-exact-active:hover {
  border-bottom: solid 0.15rem white;
}
nav a:hover {
  border-bottom: solid 0.12rem rgba(255, 255, 255, 0.5);
}

.trait {
  width: 35%;
  height: 0.1rem;
  background-color: rgba(255, 255, 255, 0.2);
  position: absolute;
  left: 8%;
  top: 50%;
  z-index: 99;
}

.links {
  margin: auto;
  width: 52%;
  padding-left: 8%;
  display: flex;
  justify-content: left;
  position: absolute;
  right: 0;
  top: 0rem;
  background-color: rgba(0, 0, 0, 0.1);
  background-image: url("./assets/bg-nav-rect.svg");
  backdrop-filter: blur(20px);
  background-size: 180%;
  background-position: center;
}
.link {
  padding-top: 5%;
  padding-bottom: 5%;
  margin: auto 3%;
}
</style>
