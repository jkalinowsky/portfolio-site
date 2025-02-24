<script setup lang="ts">
import { ref, markRaw } from 'vue';
import HomeView from "@/components/HomeView.vue";
import AboutView from "@/components/AboutView.vue";
import ProjectView from '@/components/ProjectView.vue';
import ContactView from '@/components/ContactView.vue'

const views = {
  HomeView: markRaw(HomeView),
  AboutView: markRaw(AboutView),
  ProjectView: markRaw(ProjectView),
  ContactView: markRaw(ContactView)
};

const currentView = ref(views.HomeView);
const isNavOpen = ref(false);

const changeView = (viewName: keyof typeof views) => {
  currentView.value = views[viewName];
  isNavOpen.value = false;
};


import { particlesConfig } from '@/assets/particlesConfig'
import type Container from "@tsparticles/vue3";

const particlesLoaded = async (container: typeof Container) => {
  console.log("Particles container loaded", container);
};
</script>

<template>
  <div id="app">
    <vue-particles
      id="tsparticles"
      @particles-loaded="particlesLoaded"
      :options="particlesConfig"
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
