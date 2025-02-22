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
      <img src="/src/assets/pck-logo.png" alt="">
      <h2>Website for Polish Red Cross</h2>
      <img src="/src/assets/gradient-logo.png" alt="">
    </div>
    <div class="description">
      <div class="github">
        <a href="https://github.com/Gradient-PG/OCR-Web"><img src="/src/assets/github-logo.png"> <b>Check github</b></a>
      </div>
      <p>Application is in the last stage of development (check branch dev if want too see the latest code:))</p>
      <h3>Description</h3>
      <p>This web application was developed to assist the Polish Red Cross in migrating to an
        online system for managing honorary blood donor cards. It provides an interface for
        testing and verifying results from an OCR model that extracts data from physical donor cards.</p>
      <p style="margin-top:0.5rem;"><b>Key features:</b></p>
      <ul>
        <li><b>User Authentication:</b> email-based login system where a password is sent to the email registered by an admin for verification.</li>
        <li><b>Data Validation:</b> users can review OCR-extracted data and correct any errors.</li>
        <li><b>Admin Panel:</b> allows administrators to manage cards, images, user accounts, and uploaded data.</li>
        <li><b>Security:</b> strong emphasis on data protection due to the presence of sensitive data.</li>
        <li><b>Automation:</b> the server is integrated with the OCR model to automate data processing and submission.</li>
      </ul>
      <h3>Stack</h3>
      <p><b>Backend: </b>Flask, MongoDB</p>
      <p><b>Frontend: </b>Vue, Vite, Bootstrap</p>
      <p><b>Additional tools: </b>Docker, Git, Postman</p>
      <h3>My role</h3>
      <p>
        This project was developed by scientific group Gradient for Polish Red Cross. The team working on this
        application consisted of four members and was supervised by client - a developer who is also a volunteer at PRC.
      </p>
      <p>
        My primary responsibility was frontend, which I developed mostly by myself.
        The goal for the UI was to keep it as simple and clean as possible, and I successfully achieved this.
        Additionally, I contributed to the backend to support other team members, since it was the more consuming part of our project.
        My focus was on implementing the logic and functionality of the admin panel and the application's main purpose — correcting cards data.
      </p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "@/assets/styles/projects.scss";
</style>
