<template>
  <div class="description">
    <div class="training-img">
      <img v-for="(img, i) in images" :key="i" :src="img" />
    </div>
    <div class="training-descr">
      <span>О нас</span>
      <span>Impulse hall — больше, чем просто фитнес. Это твое пространство силы.
        Мы верим, что главное в тренировках — это атмосфера и поддержка. Здесь ты найдешь не просто тренажеры, а команду единомышленников и тренеров, которые вдохновляют. 
        Наши студийные занятия, персональные тренировки и уютная зона отдыха созданы для того, чтобы ты полюбил каждый день, посвященный себе.
        Готовы изменить свою жизнь? Мы ждем именно вас!</span>
    </div>
  </div>
</template>

<script setup>
  import { ref } from "vue";
  const images = ref([
    "images/women.jpg",
    "images/shtanga.jpg"
  ])
</script>

<style scoped>
  .training-descr {
    display: flex;
    flex-direction: column;
    gap: 8px;
    padding-top: 30px;
    
    > span {
      font-size: 18px;
      line-height: 1.6;
      font-weight: 700;
      text-align: justify;
      color: var(--color-bg-light);
    }

    > span:first-child {
      font-size: 24px;
    }
  }
  .description {
    display: flex;
    flex-direction: row;
    gap: 50px;
    padding: 70px 70px 70px 70px;
  }
  .training-img {
    display: flex;
    gap: 40px;

    > img {
      width: 20vw;
      height: 45vh;
      object-fit: cover;
    }
    
    > img:first-child {
      padding-bottom: 50px;
    }
    > img:last-child {
      padding-top: 50px;
    }
  }
</style>