<template>
  <header class="header">
    <div class="header-logo">
      <img src="/icons/impulse_logo.png" alt="logo" />
    </div>
    <nav class="header-nav">
      <div class="nav-link"><a href="/">О нас</a></div>
      <div class="nav-link"><a href="/">Галерея</a></div>
      <div class="nav-link"><a href="/">Абонементы</a></div>
      <div class="nav-link"><a href="/">Контакты</a></div>
    </nav>
    <div class="header-phone">
      <span> +7 (964)-436-03-00 </span>
    </div>
  </header>
</template>

<script setup lang="ts">
defineOptions({ name: 'AppHeader' });
</script>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 128px;
  padding-left: 46px;
  padding-right: 20px;
  font-weight: var(--font-semibold);
}
.header-nav {
  display: flex;
  gap: 50px;
}
</style>
