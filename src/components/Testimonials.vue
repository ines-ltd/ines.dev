<script setup>
import { computed, ref } from 'vue'

const items = [
  {
    title: 'Barry Weaver',
    role: 'Head of Product',
    org: 'Voneous',
    img: 'voneus.png',
    content:
      "Ines Development was instrumental in the successful launch of our gigabit wireless access service. Their strategic planning, data management, and operational support were key factors in our success. We couldn't have done it without him!"
  },
  {
    title: 'Michael Armitage',
    role: 'COO',
    org: 'Broadway Partners Ltd',
    img: 'broadway.png',
    content:
      'Josh was a fantastic asset to our business, he helped improve and formalise our data strategy, while also assisting with our implementation of a reporting system. What started as a 3-month contract became 13-months as we were so impressed we outsourced our Head of Data position to him'
  }
]

const idx = ref(0)

const slide = computed(() => items.at(idx.value))

function changeSlide(direction) {
  idx.value = (idx.value + direction) % items.length
}
</script>

<template>
  <section id="testimonials" class="testimonials">
    <h2>Testimonials</h2>
    <p class="byline">
      We work incredibly hard for our clients, communicating every step of the
      way. Here's what they have to say:
    </p>
    <div class="card">
      <div class="details">
        <div class="content">{{ slide.content }}</div>
        <div class="title">{{ slide.title }}</div>
        <div class="role">{{ slide.role }} | {{ slide.org }}</div>
      </div>
      <div class="logo">
        <img class="logo-img" :src="slide.img" alt="" />
      </div>
    </div>
    <div class="toolbar">
      <span role="button" class="btn material-icons" @click="changeSlide(-1)">
        chevron_left
      </span>
      <span role="button" class="btn material-icons" @click="changeSlide(1)">
        chevron_right
      </span>
    </div>
  </section>
</template>

<style scoped>
.toolbar {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1rem;
  margin-top: 0.5rem;
}

h2 {
  font-size: 40px;
  margin-bottom: 16px;
}

.byline {
  color: var(--c-text-2);
  font-weight: bold;
  margin-bottom: 32px;
}

.toolbar .material-icons {
  font-size: 40px;
  padding: 0.5rem;
  aspect-ratio: 1/1;
  border-radius: 50%;
}

.btn:hover {
  cursor: pointer;
  background-color: var(--c-background-2);
}

.card {
  padding: 2rem;
  background-color: var(--c-background-2);
  box-sizing: border-box;
  border-radius: 8px;
  display: flex;
  flex-wrap: wrap;
  gap: 2rem;
  align-items: center;
  justify-content: center;
  width: fit-content;
  margin: auto;
}

.logo {
  width: 200px;
}

.logo-img {
  margin: auto;
  display: block;
}

.details {
  display: flex;
  flex-direction: column;
  max-width: 50ch;
}

.content {
  margin-bottom: 1rem;
}

.title {
  font-size: 20px;
  font-weight: 500;
  margin-bottom: 0.5rem;
}

.role {
  color: var(--c-text-2);
  font-weight: 500;
}
</style>
