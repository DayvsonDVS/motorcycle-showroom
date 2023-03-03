<template>
  <title>Honda Bike Website Landing Page</title>
  <section class="main">
    <header>
      <a href="#"> <img src="@/image/logo.png" class="logo" /></a>
      <ul class="navigation">
        <li v-for="title in navigation">
          <a href="#">{{ title }}</a>
        </li>
      </ul>
    </header>

    <div class="content">
      <h2>Ready To <span>Race</span></h2>
      <a href="#" class="btn"> Ride Now</a>
      <img src="@/image/CB-650R.png" class="bike" />
    </div>

    <div class="slider" ref="slider">
      <div class="slides">
        <h2><span>Engine</span><br />650 cc</h2>
        <h2><span>Max Speed</span><br />280 Kmph</h2>
      </div>
      <div class="slides">
        <h2><span>Mileage</span><br />14 Kml</h2>
        <h2><span>0-100 Kmph</span><br />4 Seconds</h2>
      </div>
      <div class="slides">
        <h2><span>Wheels</span><br />17-Inch Alloy</h2>
        <h2><span>Tyre Type</span><br />Tubeless</h2>
      </div>
    </div>

    <div class="footer">
      <ul class="sci">
        <li v-for="icon in icons">
          <a href=""><ion-icon :name="`logo-${icon}`"></ion-icon></a>
        </li>
      </ul>

      <div class="dots" ref="dot">
        <span class="dot"></span>
        <span class="dot"></span>
        <span class="dot"></span>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import 'assets/scss/main.scss'

const navigation = ['Top Features', 'Gallery', 'Store', 'Contact']
const icons = ['facebook', 'twitter', 'instagram']
const slider = ref<HTMLElement>()
const dot = ref<HTMLElement>()

onMounted(() => {
  const slides = [...slider.value!.children]
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
})
</script>

<style scoped lang="scss">
.main {
  position: relative;
  min-height: 100vh;
  background: linear-gradient(#1c1c1c, #323232);
  padding: 30px 100px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  header {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    padding: 30px 100px;
    display: grid;
    grid-auto-flow: column;
    align-items: center;
    justify-content: space-between;
    .logo {
      max-width: 80px;
    }
    .navigation {
      max-width: 50%;
      display: grid;
      grid-auto-flow: column;
      gap: 3rem;
      justify-content: space-between;
      li {
        list-style: none;
        width: max-content;
        a {
          position: relative;
          color: var(--white);
          text-decoration: none;
          transition: 0.25s;
          &:hover {
            color: var(--red);
          }
        }
      }
    }
  }
  &::before {
    content: 'Adventure';
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-size: 16vw;
    font-weight: 700;
    color: rgba(255, 255, 255, 0.05);
  }
  .slider {
    .slides {
      position: absolute;
      top: 60%;
      left: 0;
      transform: translateY(-50%);
      z-index: 10;
      width: 100%;
      display: flex;
      justify-content: space-between;
      padding: 0 100px;
      transition: 0.25s;
      opacity: 0;
      pointer-events: none;
      h2 {
        &:last-child {
          text-align: end;
        }
      }
      h2 {
        color: var(--white);
        font-size: 3em;
        span {
          color: var(--red);
          font-size: 0.5em;
          font-weight: 400;
          font-style: italic;
        }
      }
      &.active {
        top: 50%;
        opacity: 1;
      }
    }
  }
  .content {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    margin-top: 100px;
    z-index: 1;
    h2 {
      font-size: 5em;
      font-weight: 300;
      color: var(--white);
      text-align: center;
      span {
        font-weight: 700;
      }
    }
    .btn {
      display: inline-block;
      background: var(--red);
      color: var(--white);
      text-decoration: none;
      padding: 16px 36px;
      margin-top: 20px;
      border-radius: 50px;
      font-size: 1.25em;
      transition: 0.25s;
      &:hover {
        letter-spacing: 4px;
      }
    }
    .bike {
      max-width: 80%;
    }
  }
  .footer {
    position: absolute;
    bottom: 0;
    width: 100%;
    padding: 30px 100px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    z-index: 20;
    .sci {
      display: flex;
      li {
        list-style: none;
        a {
          color: var(--white);
          font-size: 2em;
          margin-right: 20px;
          transition: 0.25s;
          &:hover {
            color: var(--red);
          }
        }
      }
    }
  }
  .dots {
    display: flex;
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
}
</style>
