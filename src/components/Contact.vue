<script setup>
import { ref } from 'vue'
import Button from './Button.vue'

const form = ref(null)

function sendMessage() {
  const formData = new FormData(form.value)

  const formObject = {}

  formData.forEach((val, key) => {
    Object.assign(formObject, { [key]: val })
  })
}
</script>

<template>
  <section class="contact" id="contact">
    <h2>Contact us</h2>
    <p class="byline">
      We are always happy to discuss your ideas, big or small. Whether you have
      a clear picture of what you want, or require some consultation, send us a
      message and we'll get back to you straight away.
    </p>

    <form action="" ref="form">
      <label for="email">Email</label>
      <input
        type="email"
        name="email"
        id="email"
        required
        placeholder="Your email address"
      />

      <label for="message">Message</label>
      <textarea
        name="message"
        id="message"
        placeholder="Let us know how we can help you"
      ></textarea>
      <Button @click.prevent="sendMessage">Send</Button>
    </form>
  </section>
</template>

<style scoped>
h2 {
  font-size: 40px;
  margin-bottom: 16px;
}

.byline {
  color: var(--c-text-2);
  font-weight: bold;
  margin-bottom: 32px;
}

form {
  width: 100%;
  max-width: 600px;
  margin: auto;
  display: block;
  box-sizing: border-box;
}

label {
  display: block;
  box-sizing: border-box;
  margin-bottom: 0.5rem;
  font-size: 14px;
  font-weight: 500;
}

input,
textarea {
  font-family: inherit;
  font-size: 16px;
  display: block;
  box-sizing: border-box;
  background-color: white;
  padding: 1rem;
  margin-bottom: 1rem;
  border-radius: 8px;
  width: 100%;
}

textarea {
  height: 200px;
}
</style>
