<script setup>
const props = defineProps({
  tagline: {
    type: String,
    default: ''
  }
})
</script>

<template>
  <div class="wrapper">
    <img class="blob" src="/blob-3.png" alt="" />
    <section class="hero">
      <h1 class="title">ines<span class="aqua">.dev</span></h1>
      <p v-if="props.tagline" class="tagline">{{ props.tagline }}</p>
    </section>
  </div>
</template>

<style scoped>
.hero {
  min-height: 60vh;
  display: grid;
  place-content: center;
  text-align: center;
}

.wrapper {
  position: relative;
}

.blob {
  position: absolute;
  top: 0;
  opacity: 10%;
  width: 100%;
  max-width: 600px;
  left: 0;
  right: 0;
  margin: auto;
}

.title {
  font-size: 64px;
  font-weight: 600;
  margin-bottom: 1rem;
}

.aqua {
  color: var(--c-aqua);
}

.tagline {
  font-size: 22px;
  color: var(--c-text-2);
  font-weight: 500;
}
</style>
