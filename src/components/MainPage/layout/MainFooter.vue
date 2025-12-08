<template>
  <footer class="main-footer">
    <div class="footer-arrow-icon">
      <img src="/icons/arrow-upward-fill.svg" alt="arrow" />
    </div>
    <div class="footer-social-links">
      <a href="https://t.me/yourusername" target="_blank" rel="noopener noreferrer" class="social">
        <img src="/icons/tg-logo.svg" alt="Telegram" />
      </a>
      <a
        href="https://vk.com/yourusername"
        target="_blank"
        rel="noopener noreferrer"
        class="social"
      >
        <img src="/icons/vk-logo.svg" alt="VK" />
      </a>
    </div>
  </footer>
</template>

<script setup lang="ts"></script>

<style scoped>
.main-footer {
  position: relative;
  height: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.footer-arrow-icon img {
  width: 30px;
  height: 30px;
  cursor: pointer;
}

.footer-social-links {
  position: absolute;
  right: 20px;
  top: 50%;
  transform: translateY(-50%);
  display: flex;
  gap: 35px;
}

.footer-social-links .social img {
  width: 30px;
  height: 30px;
  cursor: pointer;
}
</style>
