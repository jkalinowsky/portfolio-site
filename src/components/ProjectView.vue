<script lang="ts">
import { markRaw } from 'vue'
import P1View from '@/components/projects/P1View.vue'
import P2View from '@/components/projects/P2View.vue'
import P3View from '@/components/projects/P3View.vue'
export default {
  data() {
    return {
      projects: [
        {name: "Project1", component: markRaw(P1View)},
        {name: "Project2", component: markRaw(P2View)},
        {name: "Project3", component: markRaw(P3View)}
      ],
      currentIndex: 0,
      currentProject: null as any,
    }
  },
  mounted() {
    this.currentProject = this.projects[this.currentIndex.value].component
  },
  methods: {
    changeProject(direction: 'prev' | 'next') {
      if (direction === 'prev') {
        this.currentIndex = (this.currentIndex - 1 + this.projects.length) % this.projects.length;
      } else {
        this.currentIndex = (this.currentIndex + 1) % this.projects.length;
      }
      this.currentProject = this.projects[this.currentIndex].component;
    }
  }
}
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
