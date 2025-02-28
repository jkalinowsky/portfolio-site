<script lang="ts">
import { markRaw } from 'vue';
import { particlesConfig } from '@/assets/particlesConfig'
import type Container from "@tsparticles/vue3";
import HomeView from "@/components/HomeView.vue"
import AboutView from "@/components/AboutView.vue"
import ProjectView from '@/components/ProjectView.vue'
import ContactView from '@/components/ContactView.vue'

export default {
  data() {
    return {
      views: {
        HomeView: markRaw(HomeView),
        AboutView: markRaw(AboutView),
        ProjectView: markRaw(ProjectView),
        ContactView: markRaw(ContactView)
      },
      currentView: this.view.HomeView,
      isNavOpen: false,
      pC: particlesConfig
    }
  },
  methods: {
    changeView(viewName: keyof typeof this.views) {
      this.currentView.value = this.views[viewName];
      this.isNavOpen.value = false;
    },
    async particlesLoaded(container: typeof Container) {
      console.log("Particles container loaded", container);
    }
  }
}
</script>

<template>
  <div id="app">
    <vue-particles
      id="tsparticles"
      @particles-loaded="particlesLoaded"
      :options="this.pC"
    />

    <keep-alive>
      <component :is="currentView" :changeView="changeView" />
    </keep-alive>


    <button class="nav-toggle" @click="isNavOpen = !isNavOpen">☰</button>
    <transition name="slide">
      <nav v-if="isNavOpen" class="navbar">
        <ul>
          <li @click="changeView('HomeView')"> Home </li>
          <li @click="changeView('AboutView')"> About me </li>
          <li @click="changeView('ProjectView')"> Projects </li>
          <li @click="changeView('ContactView')"> Contact me </li>
        </ul>
      </nav>
    </transition>
  </div>
</template>

<style lang="scss">
@import "@/assets/styles/main.scss";
@import "@/assets/styles/navbar.scss";
#app {
  position: fixed;
  width: 100%;
  min-height: 100vh;
  background-color: transparent;
}

#tsparticles {
  position: absolute;
  top: 0;
  left: 0;
  z-index: -99;
  width: 100%;
  height: 100%;
}
</style>
