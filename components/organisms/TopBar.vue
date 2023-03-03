<template>
  <div class="top-bar">
    <Logo />

    <NavTitle :navigation="['Top Features', 'Gallery', 'Store', 'Contact']" />
  </div>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
.top-bar {
  display: grid;
  grid-auto-flow: column;
  align-items: center;
  padding: 1rem 4rem;
  &:deep(.logo) {
    img {
      width: 100px;
    }
  }
}
</style>
