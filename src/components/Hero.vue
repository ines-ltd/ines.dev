<script setup>
import { onMounted, ref } from 'vue'
const glow = ref(null)
const hero = ref(null)

onMounted(() => {
  const heroEl = hero.value
  const glowEl = glow.value

  heroEl.addEventListener('mousemove', e => {
    const box = heroEl.getBoundingClientRect()
    glowEl.style.setProperty('--x', e.clientX - box.x)
    glowEl.style.setProperty('--y', e.clientY - box.y)
  })
})
</script>

<template>
  <section class="hero" ref="hero">
    <h1 class="welcome-title">
      <span>ines</span>
      <span class="text-highlight">.dev</span>
    </h1>
    <p class="tagline">Craftsmen in software and data</p>
    <img src="/seperator-1-desktop.svg" alt="" />
    <div class="glow" ref="glow"></div>
  </section>
</template>

<style scoped>
.hero {
  height: 100%;
  display: grid;
  place-content: center;
  text-align: center;
  position: relative;
  overflow: hidden;
}

.tagline {
  font-size: 1.2rem;
}

img {
  position: absolute;
  bottom: 0;
  width: 100vw;
  height: 100vh;
  object-fit: cover;
  z-index: -1;
}

.glow {
  --dim: max(100vw, 100vh);
  position: absolute;
  top: calc(var(--y, 0) * 1px - calc(var(--dim) / 2));
  left: calc(var(--x, 0) * 1px - calc(var(--dim) / 2));
  width: var(--dim);
  height: var(--dim);
  background: radial-gradient(
    closest-side,
    hsla(0, 0%, 100%, 0.2),
    hsla(0, 0%, 0%, 0)
  );
  z-index: -2;
}
</style>
