<template>
  <div class="main-page-cont">
    <Header />
    <MainDescription />
    <div class="stripes">
      <img src="./assets/Rectangle 17.png" alt="Stripe 1" />
      <img src="./assets/Rectangle 18.png" alt="Stripe 2" />
      <img src="./assets/Rectangle 19.png" alt="Stripe 3" />
      <img src="./assets/Rectangle 24.png" alt="Stripe 4" />
      <img src="./assets/Rectangle 25.png" alt="Stripe 5" />
    </div>
    <MainFooter />
  </div>
</template>

<script setup lang="ts">
import Header from '../../Header.vue';
import MainDescription from './layout/MainDescription.vue';
import MainFooter from './layout/MainFooter.vue';
defineOptions({ name: 'MainPage' });
</script>

<style scoped>
.main-page-cont {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100vh;
  background-image: url('/images/cover.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  overflow: hidden;
}

.main-page-cont::before {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(
    180deg,
    rgba(0, 0, 0, 0.9) 0%,
    rgba(0, 0, 0, 0.1) 100%,
    rgba(0, 0, 0, 0.4) 100%
  );
  z-index: 0;
}

.main-page-cont > * {
  position: relative;
  z-index: 1;
}

.stripes > img {
  position: absolute;
}

.stripes > img:nth-child(1) {
  left: -4%;
  bottom: -26vh;
  z-index: 8;
}

.stripes > img:nth-child(2) {
  left: -2%;
  bottom: -24vh;
  z-index: 10;
}

.stripes > img:nth-child(3) {
  left: -1%;
  width: 200px;
  bottom: -2vh;
  z-index: 10;
}
.stripes > img:nth-child(4) {
  left: 75%;
  bottom: 55vh;
  z-index: 10;
}
.stripes > img:nth-child(5) {
  left: 73%;
  bottom: 60vh;
  z-index: 10;
}
</style>
