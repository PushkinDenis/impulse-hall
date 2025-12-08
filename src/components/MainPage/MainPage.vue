<template>
  <div class="main-page-cont">
    <Header />
    <MainDescription />
  </div>
</template>

<script setup lang="ts">
import Header from '../../Header.vue';
import MainDescription from './layout/MainDescription.vue';
defineOptions({ name: 'MainPage' });
</script>

<style scoped>
.main-page-cont {
  height: 100vh;
  background-image: url('/images/cover.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}
</style>
