<script lang="ts">
export default {
  props: {
    changeView: Function,
  },
  data() {
    return {
      show: false,
    }
  },
  activated() {
    setTimeout(() => {
      this.show = true;
    }, 300);
  },
  deactivated() {
    this.show = false;
  }
}


</script>

<template>
  <div class="container">
    <transition name="slide">
      <h1 v-if="show">Hello, I'm <span>Jakub Kalinowski</span></h1>
    </transition>
    <transition name="slide">
      <h2 v-if="show">Junior Web Developer</h2>
    </transition>
    <div class="buttons">
      <transition name="slide-left">
        <button v-if="show" class="btn" @click="changeView('ProjectView')">
          <i class="fa-solid fa-angles-left"></i> View My Work
        </button>
      </transition>
      <transition name="slide-right">
        <button v-if="show" class="btn" @click="changeView('AboutView')">
          Get to Know Me <i class="fa-solid fa-angles-right"></i>
        </button>
      </transition>
    </div>
  </div>
</template>

<style scoped>
  @import "@/assets/styles/home.scss";
</style>
