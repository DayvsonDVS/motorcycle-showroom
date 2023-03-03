<template>
  <div class="middle">
    <div class="content">
      <h2>Ready To <span>Race</span></h2>
      <a href="#" class="btn"> Ride Now</a>
      <img src="@/image/CB-650R.png" class="bike" />
    </div>

    <Slides />
  </div>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
.middle {
  @include for-size('tablet') {
    display: grid;
    justify-items: center;
  }
  @include for-size('phone') {
    display: grid;
    justify-items: center;
  }
  .content {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    margin-top: 20px;
    z-index: 1;
    @include for-size('tablet') {
      padding-bottom: 100px;
    }
    @include for-size('phone') {
      padding-bottom: 100px;
    }
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
      max-width: 40%;
      padding-bottom: 20px;
    }
  }
}
</style>
