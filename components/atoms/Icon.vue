<template>
  <ul class="icon">
    <li v-for="icon in titles">
      <a href=""><ion-icon :name="`logo-${icon}`"></ion-icon></a>
    </li>
  </ul>
</template>

<script setup lang="ts">
interface Props {
  titles: string[]
}

const prop = defineProps<Props>()
</script>

<style scoped lang="scss">
.icon {
  display: grid;
  grid-auto-flow: column;
  justify-content: center;
  gap: 1rem;
  li {
    list-style: none;
    a {
      color: #fff;
      font-size: 2rem;
      &:hover {
        color: var(--red);
      }
    }
  }
}
</style>
