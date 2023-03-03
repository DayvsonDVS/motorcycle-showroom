<template>
  <ul class="nav-title">
    <li v-if="!menu" v-for="title in navigation">
      <a href="#">{{ title }}</a>
    </li>

    <ion-icon
      v-if="menu"
      :name="`${!isActive ? 'grid' : 'close'}-outline`"
      @click="onActive()"
    />

    <div :class="['menu', { active: isActive }]">
      <li v-if="isActive" v-for="title in navigation">
        <a href="#">{{ title }}</a>
      </li>
    </div>
  </ul>
</template>

<script setup lang="ts">
interface Props {
  navigation: string[]
}

const prop = defineProps<Props>()
const menu = ref(false)
const isActive = ref(false)
const iconMenu = ref('')

onMounted(() => {
  window.addEventListener('resize', () => {
    document.body.clientWidth <= 992
      ? (menu.value = true)
      : (menu.value = false)
  })
})

function onActive() {
  isActive.value = !isActive.value
}
</script>

<style scoped lang="scss">
.nav-title {
  display: grid;
  grid-auto-flow: column;
  justify-content: end;
  li {
    list-style: none;
    padding-right: 2rem;
    a {
      text-decoration: none;
      color: #fff;
      &:hover {
        color: var(--red);
      }
    }
  }
  ion-icon {
    display: grid;
    justify-content: end;
    color: #fff;
    font-size: 30px;
    cursor: pointer;
    z-index: 50;
    &:hover {
      color: var(--red);
    }
  }
  .menu {
    &.active {
      align-content: baseline;
      background: linear-gradient(#1c1c1c, #323232);
      display: grid;
      gap: 2rem;
      justify-content: center;
      left: 0;
      min-height: 130%;
      padding-top: 25%;
      position: absolute;
      top: 0;
      width: 100%;
      z-index: 40;
    }
  }
}
</style>
