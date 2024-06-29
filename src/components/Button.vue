<template>
  <button class="btn">
    <slot name="default"></slot>
  </button>
</template>

<style scoped>
.btn {
  font-size: 16px;
  padding: 5px 10px;
  background-color: var(--c-aqua);
  color: var(--c-text-inverse);
  border-radius: 8px;
  font-weight: 600;
}
</style>
