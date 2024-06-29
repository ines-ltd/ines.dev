<script setup>
import Button from './Button.vue'

const props = defineProps({
  title: {
    type: String,
    default: 'Site Title'
  }
})

const links = ['Services', 'Team', 'Testimonials']
</script>

<template>
  <header>
    <div class="navbar">
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
        <Button>Get in touch</Button>
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
}

.navbar {
  height: var(--nav-height);
  padding: 0 16px;
  display: flex;
  align-items: center;
  justify-content: space-between;
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
