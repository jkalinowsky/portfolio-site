<script setup lang="ts">
  import P1View from '@/components/projects/P1View.vue'
  import P2View from '@/components/projects/P2View.vue'
  import { markRaw, ref } from 'vue'

  const projects = [
    { name: "Project1", component: markRaw(P1View) },
    { name: "Project2", component: markRaw(P2View) },
  ];

  const currentIndex = ref(0);
  const currentProject = ref(projects[currentIndex.value].component);
  const isNavOpen = ref(false);

  const changeProject = (direction: 'prev' | 'next') => {
    if (direction === 'prev') {
      currentIndex.value = (currentIndex.value - 1 + projects.length) % projects.length;
    } else {
      currentIndex.value = (currentIndex.value + 1) % projects.length;
    }
    currentProject.value = projects[currentIndex.value].component;
  };
 </script>

<template>
  <button class="nav-toggle" @click="isNavOpen = !isNavOpen">☰</button>
  <div class="container">

    <transition name="slide">
      <nav v-if="isNavOpen" class="navbar">
        <ul>
          <li> Home </li>
          <li> About me </li>
          <li> Contact </li>
        </ul>
      </nav>
    </transition>

    <div class="project-header">
      <button @click="changeProject('prev')" class="arrow-button left">&#9665;</button>
      <h1 class="h-projects">Projects</h1>
      <button @click="changeProject('next')" class="arrow-button right">&#9655;</button>
    </div>
    <keep-alive>
      <component :is="currentProject"  :changeProject="changeProject" />
    </keep-alive>
  </div>
</template>

<style lang="scss" scoped>
  @import "@/assets/styles/projects.scss";
  @import "@/assets/styles/navbar.scss";
</style>
