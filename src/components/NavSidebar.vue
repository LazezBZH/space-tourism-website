<template>
  <div class="sidebar">
    <div
      class="sidebar-backdrop"
      @click="closeSidebarPanel"
      v-if="isPanelOpen"
    ></div>
    <transition name="slide">
      <div v-if="isPanelOpen" class="sidebar-panel">
        <slot></slot>
      </div>
    </transition>
  </div>
</template>
<script>
import { store, mutations } from "@/store.js";

export default {
  methods: {
    closeSidebarPanel: mutations.toggleNav,
  },
  computed: {
    isPanelOpen() {
      return store.isNavOpen;
    },
  },
};
</script>
<style>
@media screen and (min-width: 601px) {
  .sidebar {
    display: none;
  }
}

.sidebar {
  position: absolute;
  top: 0;
  margin: 0;
}
.slide-enter-active,
.slide-leave-active {
  transition: transform 0.2s ease;
}

.slide-enter,
.slide-leave-to {
  transform: translateX(-100%);
  transition: all 10ms ease-in 0s;
}

.sidebar-backdrop {
  background-color: transparent;
  width: 100vw;
  height: 100vh;
  position: fixed;
  top: 2%;
  left: 0;
  cursor: pointer;
  margin: 0;
}
.sidebar-panel {
  overflow-y: auto;

  position: fixed;
  right: 0;

  top: 0.3rem;
  height: 100vh;
  margin: 0;
  padding: 0;
  width: 70%;
}
</style>
