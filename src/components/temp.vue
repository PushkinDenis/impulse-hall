<template>
  <div
    class="carousel"
    @mouseenter="stopAutoplay"
    @mouseleave="startAutoplay"
  >
    <!-- окно -->
    <div class="carousel-window">
      <div
        class="carousel-track"
        :style="{ transform: `translateX(-${currentGroup * 100}%)` }"
      >
        <!-- ПОКАЗЫВАЕТСЯ ТОЛЬКО 1 ГРУППА ЗА РАЗ -->
        <div
          class="carousel-group"
          v-for="(group, g) in groups"
          :key="g"
        >
          <div
            class="carousel-item"
            v-for="(img, i) in group"
            :key="i"
          >
            <img :src="img" />
          </div>
        </div>
      </div>
    </div>

    <!-- нижний слайдер -->
    <div class="slider-bar">
      <div class="slider-track">
        <div
          class="slider-thumb"
          :style="{
            left: `${currentGroup * (100 / groups.length)}%`,
            width: `${100 / groups.length}%`
          }"
        ></div>
      </div>

      <!-- клики по прямоугольным сегментам -->
      <div class="slider-clicks">
        <div
          v-for="(_, index) in groups.length"
          :key="index"
          class="slider-segment"
          @click="goToGroup(index)"
        ></div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed, onMounted, onBeforeUnmount } from "vue";

// твои 9 изображений
const images = [
  "/img/1.jpg",
  "/img/2.jpg",
  "/img/3.jpg",
  "/img/4.jpg",
  "/img/5.jpg",
  "/img/6.jpg",
  "/img/7.jpg",
  "/img/8.jpg",
  "/img/9.jpg",
];

// ------------------------------------------
// ТУТ МЫ ДЕЛАЕМ РОВНО 3 ГРУППЫ ПО 3 ИЗОБРАЖЕНИЯ
// ------------------------------------------
const groups = computed(() => [
  images.slice(0, 3),
  images.slice(3, 6),
  images.slice(6, 9)
]);

const currentGroup = ref(0);

// переключение группы
function next() {
  currentGroup.value = (currentGroup.value + 1) % groups.value.length;
}

function goToGroup(i) {
  currentGroup.value = i;
}

// autoplay ----------------------------
const autoplayInterval = ref(null);
const AUTOPLAY_DELAY = 3000;

function startAutoplay() {
  stopAutoplay();
  autoplayInterval.value = setInterval(() => next(), AUTOPLAY_DELAY);
}

function stopAutoplay() {
  if (autoplayInterval.value) {
    clearInterval(autoplayInterval.value);
    autoplayInterval.value = null;
  }
}

onMounted(() => startAutoplay());
onBeforeUnmount(() => stopAutoplay());
</script>

<style scoped>
.carousel {
  width: 900px;
  margin: auto;
}

.carousel-window {
  overflow: hidden;
  width: 100%;
  height: 300px;
  border-radius: 10px;
}

.carousel-track {
  display: flex;
  transition: transform 0.5s ease;
  height: 100%;
}

.carousel-group {
  display: flex;
  width: 100%;
  flex-shrink: 0; /* важно — чтобы группа была отдельным слайдом */
}

.carousel-item {
  width: calc(100% / 3);
  height: 100%;
  padding: 5px;
}
.carousel-item img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

/* нижний слайдер */
.slider-bar {
  margin-top: 15px;
  position: relative;
}

.slider-track {
  position: relative;
  height: 6px;
  background: #ddd;
  border-radius: 3px;
}

.slider-thumb {
  position: absolute;
  top: 0;
  height: 100%;
  background: #42b983;
  border-radius: 3px;
  transition: left 0.5s ease;
}

.slider-clicks {
  position: absolute;
  top: -8px;
  left: 0;
  width: 100%;
  height: 20px;
  display: flex;
}

.slider-segment {
  flex: 1;
  cursor: pointer;
}
</style>