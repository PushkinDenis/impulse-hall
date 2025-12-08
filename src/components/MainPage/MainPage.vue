<template>
  <div class="main-page-cont">
    <Header />
    <MainDescription />
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
  position: relative; /* для ::before */
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
</style>
