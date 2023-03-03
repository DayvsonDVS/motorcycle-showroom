<template>
  <div class="footer">
    <SocialLink />
    <Dots />
  </div>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
.footer {
  display: grid;
  grid-template-columns: max-content max-content;
  justify-content: space-between;
  padding: 0rem 5rem;
}
</style>
