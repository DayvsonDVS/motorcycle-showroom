<template>
  <div class="slider" ref="slider">
    <div v-for="slide in sliders" class="slides">
      <h2>
        <span>{{ slide.title1 }}</span
        ><br />{{ slide.subTitle1 }}
      </h2>
      <h2>
        <span>{{ slide.title2 }}</span
        ><br />{{ slide.subTitle2 }}
      </h2>
    </div>
  </div>
</template>

<script setup lang="ts">
const sliders = [
  {
    title1: 'Engine',
    title2: 'Max Speed',
    subTitle1: '650 cc',
    subTitle2: '280 Kmph'
  },
  {
    title1: 'Mileage',
    title2: '0-100 Kmph',
    subTitle1: '14 Kml',
    subTitle2: '4 Seconds'
  },
  {
    title1: 'Wheels',
    title2: 'Tyre Type',
    subTitle1: '17-Inch Alloy',
    subTitle2: 'Tubeless'
  }
]
</script>

<style scoped lang="scss">
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
    transition: 0.3s;
    opacity: 0;
    pointer-events: none;
    @include for-size('phone') {
      top: 80%;
    }
    @include for-size('tablet') {
      top: 80%;
    }
    h2 {
      &:last-child {
        text-align: end;
        @include for-size('tablet') {
          text-align: center;
        }
        @include for-size('phone') {
          text-align: center;
        }
      }
    }
    h2 {
      color: var(--white);
      font-size: 3em;
      @include for-size('tablet') {
        text-align: center;
      }
      @include for-size('phone') {
        text-align: center;
      }
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
      @include for-size('tablet') {
        top: 900px;
        position: inherit;
        display: grid;
        grid-auto-flow: row;
      }
      @include for-size('phone') {
        top: 900px;
        position: inherit;
        display: grid;
        grid-auto-flow: row;
      }
    }
  }
}
</style>
