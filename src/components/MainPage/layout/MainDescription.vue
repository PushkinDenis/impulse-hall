<template>
  <main>
    <div class="main-cont">
      <h1 class="main-head">Фитнес клуб impuls hall</h1>
      <p class="main-p">Лучший среди конкурентов</p>
      <Button variant="custom">Получить консультацию</Button>
    </div>
  </main>
</template>

<script setup lang="ts">
import Button from '../../../Button.vue';
defineOptions({ name: 'MainDescription' });
</script>

<style scoped>
.main-head {
  font-weight: var(--font-bold);
  font-size: 64px;
}
.main-p {
  font-weight: var(--font-medium);
  font-size: 28px;
}
.main-cont {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  max-width: fit-content;
  gap: 35px;
  margin: 0 auto;
}
</style>
