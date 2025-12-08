<template>
  <div class="description-icons">
    <div class="icons">
      <div
        class="icons-item"
        v-for="(obj, i) in icons"
        :key="i"
      >
        <img :src="obj.img" />
        <span>{{ obj.descr }}</span>
      </div>
    </div>
    
  </div>
</template>

<script setup>
  import { ref } from "vue";
  const icons = ref([
    { descr: 'Полностью укомплектованный зал', img: "images/cycle.png" },
    { descr: 'Профессиональное оборудование', img: "images/dumbbell.png" },
    { descr: 'Удобное расположение в центре города', img: "images/location.png" },
    { descr: 'Доступная стоимость занятий', img: "images/wallet.png" },
  ])
</script>

<style scoped>
  .description-icons {
    display: flex;
    width: auto;
    height: 200px;
    padding-left: 50px;
    padding-right: 50px;
    padding-bottom: 50px;

    > .icons {
      display: flex;
      flex-direction: row;
      gap: 16px;
      width: 100%;
      height: 100%;
    }
  }
  .icons-item {
    display: flex;
    width: 100%;
    height: 80px;
    flex-direction: row;
    align-items: center;
    gap: 25px;
    > span {
      color: var(--color-bg-light)
    }
    &:hover {
      border-bottom: 3px solid var(--color-orange);
    }
  }
</style>