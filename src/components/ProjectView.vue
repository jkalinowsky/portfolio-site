<script setup lang="ts">
  import P1View from '@/components/projects/P1View.vue'
  import P2View from '@/components/projects/P2View.vue'
  import P3View from '@/components/projects/P3View.vue'
  import { markRaw, ref } from 'vue'

  const projects = [
    { name: "Project1", component: markRaw(P1View) },
    { name: "Project2", component: markRaw(P2View) },
    { name: "Project3", component: markRaw(P3View) }
  ];

  const currentIndex = ref(0);
  const currentProject = ref(projects[currentIndex.value].component);

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
  <div class="container">
    <div class="project-header">
      <button @click="changeProject('prev')" class="arrow-button left">&#9665;</button>
      <h1 class="h-title">Projects</h1>
      <button @click="changeProject('next')" class="arrow-button right">&#9655;</button>
    </div>
    <div class="content">
      <keep-alive>
        <component :is="currentProject"  :changeProject="changeProject" />
      </keep-alive>
    </div>
  </div>
</template>

<style lang="scss" scoped>
  @import "@/assets/styles/projects.scss";
</style>
