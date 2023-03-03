<template>
  <div class="dots" ref="dot">
    <span :class="['dot', { active: state }]" v-for="(dot, index) in 3"></span>
  </div>
</template>

<script setup lang="ts">
const state = ref(false)
const dot = ref<HTMLElement>()

onMounted(() => {
  setTimeout(() => {
    const slides = [...document.querySelector('.slider')!.children]
    const dots = [...dot.value!.children]

    dots.map((dot, index) => {
      dot.addEventListener('click', () => {
        removeClass()
        slides[index].classList.add('active')
        dots[index].classList.add('active')
      })
    })

    function removeClass() {
      const listRemoveClass = [...dots, ...slides]
      listRemoveClass.map((el) => {
        el.classList.remove('active')
      })
    }
  }, 55)
})
</script>

<style scoped lang="scss">
.dots {
  display: grid;
  grid-auto-flow: column;
  justify-content: center;
  .dot {
    width: 10px;
    height: 10px;
    background: rgba(255, 255, 255, 0.2);
    border-radius: 50%;
    cursor: pointer;
    margin-left: 10px;
    &.active {
      background: var(--white);
    }
  }
}
</style>
