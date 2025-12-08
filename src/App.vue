<script setup lang="ts">
  import Button from './Button.vue';
  import DescriptionPage from "./components/DescriptionPage/DescriptionPage.vue";
  import MembershipPage from "./components/MembershipPage/MembershipPage.vue";
</script>

<template>
  <div class="container">
    <div>cscsc</div>
    <Button>{{ 'Получить консультацию' }}</Button>
    <Button color="orange">{{ 'Получить консультацию' }}</Button>
    <Button variant="custom">{{ 'Получить консультацию' }}</Button>
    <Button>{{ 'Зарегестрироваться' }}</Button>
  </div>
  <DescriptionPage/>
  <MembershipPage/>
</template>

<style scoped>
.container {
  display: flex;
  height: 100vh;
  width: 100%;
  justify-content: center;
  align-items: center;
}
</style>
