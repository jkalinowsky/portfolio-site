<script setup lang="ts">
import { ref, markRaw } from 'vue';
import HomeView from "@/components/HomeView.vue";
import AboutView from "@/components/AboutView.vue";
import ProjectView from '@/components/ProjectView.vue';

const views = {
  HomeView: markRaw(HomeView),
  AboutView: markRaw(AboutView),
  ProjectView: markRaw(ProjectView)
};

const currentView = ref(views.HomeView);

const changeView = (viewName: keyof typeof views) => {
  currentView.value = views[viewName];
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
  </div>
</template>

<style lang="scss">
@import "@/assets/styles/main.scss";
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
