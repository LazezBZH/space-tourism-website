<template>
  <nav class="main-nav">
    <img alt="logo" src="/assets/shared/logo.svg" />
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
  <div id="burger">
    <nav class="burger-nav">
      <img alt="logo" src="/assets/shared/logo.svg" />
      <NavBurger></NavBurger>
    </nav>

    <NavSidebar>
      <ul class="sidebar-panel-nav">
        <li>
          <router-link v-on:click="toggle" class="link link_1" to="/"
            ><span class="bold">00</span> HOME</router-link
          >
        </li>
        <li>
          <router-link v-on:click="toggle" class="link link_2" to="/destination"
            ><span class="bold">01</span> DESTINATION</router-link
          >
        </li>
        <li>
          <router-link v-on:click="toggle" class="link link_3" to="/crew"
            ><span class="bold">02</span> CREW</router-link
          >
        </li>
        <li>
          <router-link v-on:click="toggle" class="link link_4" to="/technology"
            ><span class="bold">03</span> TECHNOLOGY</router-link
          >
        </li>
      </ul>
    </NavSidebar>
  </div>
</template>

<script>
import NavBurger from "./components/NavBurger.vue";
import NavSidebar from "./components/NavSidebar.vue";
import { mutations } from "@/store.js";

export default {
  name: "app",
  components: {
    NavBurger,
    NavSidebar,
  },
  methods: {
    toggle() {
      mutations.toggleNav();
    },
  },
};
</script>

<style>
* {
  margin: 0.2rem auto;
  box-sizing: content-box;
}
#app {
  position: relative;
  max-width: 1440px;
  height: auto;
  padding-bottom: 5rem;
  margin-top: 0;
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
  margin: 0 auto auto 0;
  padding-top: 2%;
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
  padding-top: 2%;
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
.burger-nav {
  display: none;
}
@media screen and (min-width: 601px) and (max-width: 999px) {
  .links {
    width: 70%;
    justify-content: right;
  }
  .trait {
    width: 20%;
  }
}
@media screen and (max-width: 849px) {
  .bold {
    display: none;
  }
}

@media screen and (max-width: 600px) {
  .bold {
    font-family: "Barlow Condensed", sans-serif;
    display: block;
    margin: 0;
    padding-right: 1rem;
    font-size: 1.7rem;
    font-weight: 400;
    letter-spacing: 2px;
  }
  .burger-nav {
    display: block;
    margin-top: 0;
  }

  .main-nav {
    display: none;
  }

  .burger-nav img {
    margin: 1.5rem 0.5rem;
    width: 2.2rem;
    height: 2.2rem;
  }
  .burger-nav {
    display: flex;
    justify-content: space-between;
    padding: 0;
    margin: 0;
  }
  .sidebar-panel {
    height: auto;
    background-color: rgba(0, 0, 0, 0.1);
    background-image: url("./assets/bg-nav-rect.svg");
    backdrop-filter: blur(10px);
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
    padding-bottom: 15rem;
  }
  ul {
    margin-top: 6rem;
  }
  ul.sidebar-panel-nav {
    list-style-type: none;
  }
  ul.sidebar-panel-nav li a {
    font-family: "Barlow Condensed", sans-serif;
    color: #fff;
    font-weight: 200;
    letter-spacing: 0.5px;
    text-decoration: none;
    font-size: 1.7rem;
    display: flex;
    padding: 1.5rem 0.5rem;
  }
}
</style>
