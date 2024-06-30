<script setup>
import Header from './components/Header.vue'
import Hero from './components/Hero.vue'
import Services from './components/Services.vue'
import Team from './components/Team.vue'
import Testimonials from './components/Testimonials.vue'
import Contact from './components/Contact.vue'
import Footer from './components/Footer.vue'

const settings = {
  title: 'ines.dev',
  tagline: 'Craftsmen in software and data'
}
</script>

<template>
  <div class="layout">
    <Header :title="settings.title" />
    <div class="content">
      <Hero :tagline="settings.tagline" />
      <Services />
      <Team />
      <Testimonials />
      <Contact />
    </div>
    <Footer></Footer>
  </div>
</template>

<style scoped>
.layout {
  height: 100vh;
  display: grid;
  grid-template-rows: auto 1fr;
}

.header {
  position: sticky;
  top: 0;
  height: var(--nav-height);
}

.content {
  width: 100%;
  padding: 1rem;
  max-width: var(--content-max-width);
  margin-inline: auto;
  box-sizing: border-box;
  padding-bottom: 128px;
}
</style>
