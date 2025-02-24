<script lang="ts">
import axios from 'axios';

export default {
  data() {
    return {
      email: '',
      message: '',
      statusMessage: '',
      statusClass: '',
    };
  },
  methods: {
    async handleSubmit() {
      try {
        const response = await axios.post('https://formspree.io/f/xrbewqrw', {
          email: this.email,
          message: this.message,
        });

        if (response.status === 200) {
          this.statusMessage = 'Message sent successfully!';
          this.statusClass = 'success';
        } else {
          this.statusMessage = 'There was an error sending your message.';
          this.statusClass = 'error';
        }

        this.email = '';
        this.message = '';
        // eslint-disable-next-line @typescript-eslint/no-unused-vars
      } catch (error) {
        this.statusMessage = 'There was an error with the submission.';
        this.statusClass = 'error';
      }
    }
  }
}
</script>


<template>
  <div class="container">
    <h1 class="h-title">Contact me</h1>
    <div>
      <form class="form" @submit.prevent="handleSubmit">
        <label>
          Your email:
          <input v-model="email" type="email" name="email" required />
        </label>
        <label>
          Your message:
          <textarea v-model="message" name="message" required></textarea>
        </label>
        <button class="btn" style="width:50%;" type="submit">Send</button>
      </form>
      <div v-if="statusMessage" :class="statusClass">{{ statusMessage }}</div>
    </div>
  </div>
</template>

<style lang="scss">
@import "@/assets/styles/contact.scss";
</style>
