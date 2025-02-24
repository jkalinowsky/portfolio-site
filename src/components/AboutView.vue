<template>
  <div class="container">
    <h1 class="h-title">About</h1>
    <div class="two-col">
      <div class="about-me">
        <p>
          Hello! My name is Kuba, and I'm a web developer. On a daily basis, I'm pursuing my
          Bachelor’s Degree in Computer Science, currently in my second year. During my studies,
          I've acquired knowledge in many areas, including low-level programming (MASM and C) or
          web development. It has also helped me learn how to work under pressure and meet deadlines,
          even in the worst scenarios.
        </p>
        <p>
          At present, apart from my studies, I develop my own projects (more information
          in the projects section) and participate in projects from the scientific group at my university.
          In previous projects, I focused on frontend development, and now I'm expanding my knowledge
          in the other side of web applications - backend development. I'm currently learning Spring and PostgreSQL
          while working on my newest project: quiz application for students. Thanks to the scientific
          group, I've learned how to work as a team, work under pressure and handle real clients' demands.
        </p>
      </div>
      <div class="stack">
        <div class="row">
          <h3>Languages</h3>
          <div class="images-row">
            <div class="image-container">
              <img src="@/assets/c++.png" alt="">
              <span class="image-text">C++</span>
            </div>
            <div class="image-container">
              <img src="@/assets/c.png" alt="">
              <span class="image-text">C</span>
            </div>
            <div class="image-container">
              <img src="@/assets/python.png" alt="">
              <span class="image-text">Python</span>
            </div>
            <div class="image-container">
              <img src="@/assets/js.png" alt="">
              <span class="image-text">JavaScript</span>
            </div>
            <div class="image-container">
              <img src="@/assets/ts.png" alt="">
              <span class="image-text">TypeScript</span>
            </div>
            <div class="image-container">
              <img src="@/assets/sass.png" alt="">
              <span class="image-text">Sass</span>
            </div>
            <div class="image-container">
              <img src="@/assets/java.png" alt="">
              <span class="image-text">Java</span>
            </div>
          </div>
        </div>

        <div class="row">
          <h3>Frameworks</h3>
          <div class="images-row">
            <div class="images-row">
              <div class="image-container">
                <img src="@/assets/vue.png" alt="">
                <span class="image-text">Vue</span>
              </div>
              <div class="image-container">
                <img src="@/assets/flask.png" alt="">
                <span class="image-text">Flask</span>
              </div>
              <div class="image-container">
                <img src="@/assets/spring.png" alt="">
                <span class="image-text">Spring</span>
              </div>
            </div>
          </div>
        </div>
        <div class="row">
          <h3>Tools</h3>
          <div class="images-row">
            <div class="image-container">
              <img src="@/assets/git.png" alt="">
              <span class="image-text">Git</span>
            </div>
            <div class="image-container">
              <img src="@/assets/docker.png" alt="">
              <span class="image-text">Docker</span>
            </div>
            <div class="image-container">
              <img src="@/assets/postgresql.png" alt="">
              <span class="image-text">PostgreSQL</span>
            </div>
        </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
@import "@/assets/styles/about.scss";
</style>
<script setup lang="ts">
</script>
