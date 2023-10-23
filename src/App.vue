<script setup>
import Header from './components/Header.vue'
import Hero from './components/Hero.vue'
import About from './components/About.vue'
import Services from './components/Services.vue'
import Portfolio from './components/Portfolio.vue'
import Testimonials from './components/Testimonials.vue'
</script>

<template>
  <main>
    <Hero />
    <About />
    <!-- <section id="services">
      <Services />
    </section> -->
    <!-- <section id="portfolio">
      <Portfolio />
    </section> -->
    <!-- <section id="testimonials">
      <Testimonials />
    </section> -->
  </main>
  <!-- <Blog /> -->
  <!-- <Contact /> -->
  <!-- <Footer /> -->
</template>

<style scoped>
main {
  height: 100%;
  overflow: auto;
  scroll-snap-type: y mandatory;
}

main > section {
  min-height: 100%;
}
</style>
