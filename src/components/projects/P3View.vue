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
      <h2>Quiz application for students</h2>
    </div>
    <div class="description">
      <p>The application is <b>still in development</b>, and the code is not yet public.
        However, if you're interested in the project, feel free to reach out.</p>

      <h3>Description and idea</h3>
      <p>
        To overcome the paywalls in popular quiz or flashcards applications, my friend and I decided
        to create our own platform—one that helps students prepare for their exams without limitations.
      </p>
      <p>
        This project is developed by two students, with me as the product owner. Our goal is to
        provide a free and effective learning tool, since in our opinion, a student-driven initiative
        is the best advantage over university restrictions.
      </p>
      <p style="margin-top:0.5rem;"><b>Key objectives:</b></p>
      <ul>
        <li><b>User Authentication:</b> two types of authorization - standard and student specific,
          granting access to exclusive learning materials.</li>
        <li><b>Learning System:</b> a variety of flashcards types and learning algorithm designed
          to improve study efficiency </li>
        <li><b>Admin Panel:</b> tools for managing flashcards, users and study groups.</li>
        <li><b>Website Appearance:</b> a strong focus on clean, intuitive and response website.</li>
      </ul>
      <h3>Stack</h3>
      <p><b>Backend: </b>Java Spring Boot, PostgreSQL</p>
      <p><b>Frontend: </b>Vue, Vite, Bootstrap</p>
      <p><b>Additional tools: </b>Docker, Git, Postman</p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "@/assets/styles/projects.scss";
</style>
