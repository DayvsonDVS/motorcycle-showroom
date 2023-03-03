<template>
  <div class="index">
    <TopBar />
    <Middle />
    <Footer />
  </div>
</template>

<script setup lang="ts">
import 'assets/scss/main.scss'
</script>

<style scoped lang="scss">
.index {
  display: grid;
  align-content: space-between;
  min-height: 100vh;
}
</style>
