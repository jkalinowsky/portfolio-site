<script setup lang="ts">
defineProps(['changeView']);
</script>

<template>
  <div class="container">
    <h1>Hello, I'm <span>Jakub Kalinowski</span></h1>
    <h2>Junior Web Developer</h2>
    <div class="buttons">
      <button @click="changeView('ProjectView')">
        <i class="fa-solid fa-angles-left"></i> View My Work
      </button>
      <button @click="changeView('AboutView')">
        Get to Know Me <i class="fa-solid fa-angles-right"></i>
      </button>
    </div>
  </div>
</template>

<style scoped>
  @import "@/assets/styles/home.scss";
</style>
