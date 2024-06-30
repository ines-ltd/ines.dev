<script setup>
import { ref, onMounted } from 'vue'
import Button from './Button.vue'

const props = defineProps({
  title: {
    type: String,
    default: 'Site Title'
  }
})

const links = ['Services', 'Team', 'Testimonials']

let y = ref(0)

onMounted(() => {
  window.addEventListener('scroll', () => {
    y.value = window.scrollY
  })
})
</script>

<template>
  <header>
    <div
      :class="{
        navbar: true,
        'navbar--border': y > 0
      }"
    >
      <div class="title">
        <img class="logo" src="/logo.svg" alt="" />
        <span class="title-text">{{ props.title }}</span>
      </div>
      <div class="links">
        <a
          v-for="link in links"
          :key="link"
          :href="`#${link.toLowerCase()}`"
          class="link"
        >
          {{ link }}
        </a>
        <a href="#contact">
          <Button>Get in touch</Button>
        </a>
      </div>
    </div>
  </header>
</template>

<style scoped>
header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background-color: var(--c-background-transparent);
  backdrop-filter: blur(6px);
  z-index: 999;
}

.navbar {
  height: var(--nav-height);
  padding: 0 16px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  border-bottom: solid 1px transparent;
  transition: border-bottom 0.5s;
}

.navbar--border {
  border-bottom: solid 1px var(--c-border);
}

.title {
  display: flex;
  gap: 1rem;
  align-items: center;
}

.title-text {
  font-size: 20px;
  font-weight: 600;
}

.logo {
  width: 36px;
}

.links {
  display: flex;
  gap: 1rem;
  align-items: center;
}

@media (max-width: 768px) {
  .link {
    display: none;
  }
}
</style>
