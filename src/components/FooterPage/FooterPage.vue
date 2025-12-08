<template>
  <div class="footer-block">
    <div class="impulse-icon">
        <img src="/icons/impulse_logo.png" alt="logo" />
        <span>©  Все права защищены</span>
        <span>Владивосток, 2025</span>
    </div>
    <div class="links-block">
        <div class="links">
            <span>О нас</span>
            <span>Галерея</span>
            <span>Абонементы</span>
        </div>
        <div class="links">
            <span>Контакты</span>
            <span>Связь</span>
            <span>Регистрация</span>
        </div>
        <div class="links">
            <span>Абонементы</span>
            <span>Абонементы по времени </span>
            <span>Разовые тренировки</span>
        </div>
        <div class="links">
            <span>Наши соц. сети</span>
            <div class="links-icons">
                <img src="/icons/tg-logo.svg">
                <img src="/icons/vk-logo.svg">
            </div>
        </div>
    </div>
    <div class="address">
        <span>г. Владивосток ул.Попова д.18</span>
        <span>Ежедневно с 8:00 до 23:00</span>
        <span>+7 (964)-436-03-00</span>
        <span>Политика конфиденциальности</span>
    </div>
  </div>
</template>

<style scoped>
  .footer-block {
    display: flex;
    flex-direction: row;
    width: 100%;
    height: 200px;
    gap: 70px;
    background: var(--color-bg);
    color: var(--color-bg-light);
  }
  .impulse-icon {
    display: flex;
    flex-direction: column;
    width: 300px;
    height: 100%;

    > img {
        height: 100%;
    }
    > span {
        text-align: center;
        align-content: center;
        height: 100%;
    }
  }
  .links-block {
    display: flex;
    flex-direction: row;
    gap: 30px;
  }
  .links {
    display: flex;
    flex-direction: column;
    gap: 5px;
    
    > span {
        text-align: center;
        align-content: center;
        height: 20%;
    }
  }
  .links-icons {
    display: flex;
    flex-direction: row;
    align-items: center;
    gap: 20px;
  }
  .address {
    display: flex;
    flex-direction: column;
    gap: 15px;

    > span {
        text-align: center;
        align-content: center;
        height: 100%;
    }
  }
</style>

<script setup lang="ts">
</script>