<script lang="ts">
export default {
  props: {
    changeProject: {
      type: Function,
      required: true
    }
  },
}

</script>

<template>
  <div class="project-container">
    <div class="title">
      <h2>Portfolio webiste</h2>
    </div>
    <div class="description">
      <div class="github">
        <a href="https://github.com/jkalinowsky/portfolio-site/"><img src="/src/assets/github-logo.png"> <b>Check github</b></a>
      </div>
      <h3>Description</h3>
      <p>
        This is my personal portfolio website where I showcase my projects, skills and experience,
        way more than what’s in my CV. It allows you to explore my work, technologies I use,
        and know me a little more.</p>
      <p>
        If you have any feedback about this website or would like to collaborate, feel free to
        visit 'Contact me' and leave me a message!
      </p>
      <h3>Stack</h3>
      <p><b>Frontend: </b>Vue, Vite, saas</p>
      <p><b>Other:</b> Github Pages (for deployment), git</p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "@/assets/styles/projects.scss";
</style>
