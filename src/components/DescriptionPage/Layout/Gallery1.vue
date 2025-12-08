<template>
  <div class="gallery-container">
    <h2 class="title">Галерея</h2>

    <!-- стрелки -->
    <button class="arrow arrow-left" @click="prevGroup">←</button>
    <button class="arrow arrow-right" @click="nextGroup">→</button>

    <!-- картинки -->
    <div class="gallery-wrapper">
      <div
        class="gallery-track"
        :style="{
          transform: `translateX(-${currentGroup * (100 / groups.length)}%)`,
          transition: 'transform 0.6s ease'
        }"
      >
        <div v-for="(group, index) in groups" :key="index" class="gallery-group">
          <img v-for="(img, i) in group" :key="i" :src="img" class="image" />
        </div>
      </div>
    </div>

    <!-- нижний слайдер -->
    <div class="slider-bar" @click="onSliderClick($event)">
      <div
        class="slider-thumb"
        :style="{
            left: `${currentGroup * (100 / groups.length)}%`,
            width: `${100 / groups.length}%`
          }"
      ></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "gallery",
  props: {
    images: Array
  },
  data() {
    return {
      currentGroup: 0
    };
  },
  computed: {
    groups() {
      const chunk = (arr, size) =>
        Array.from({ length: Math.ceil(arr.length / size) }, (_, i) =>
          arr.slice(i * size, i * size + size)
        );
      return chunk(this.images, 3); // группы по 3 фото
    }
  },
  mounted() {
    this.startAutoscroll();
  },
  beforeUnmount() {
    clearInterval(this.timer);
  },
  methods: {
    nextGroup() {
      this.currentGroup =
        (this.currentGroup + 1) % this.groups.length;
    },
    prevGroup() {
      this.currentGroup =
        (this.currentGroup - 1 + this.groups.length) % this.groups.length;
    },
    startAutoscroll() {
      this.timer = setInterval(() => {
        this.nextGroup();
      }, 4000);
    },
    onSliderClick(e) {
      const bar = e.currentTarget;
      const clickX = e.offsetX;
      const percent = clickX / bar.clientWidth;

      const newIndex = Math.round(percent * (this.groups.length - 1));
      this.currentGroup = newIndex;
    }
  }
};
</script>

<style scoped>
.gallery-container {
  width: 60vw;
  margin: 0 auto;
  position: relative;
  color: var(--color-bg-light);
  object-fit: cover;
}

.title {
  text-align: center;
  margin-bottom: 20px;
  font-size: 26px;
  font-weight: bold;
  color: var(--color-bg-light);
}

.gallery-wrapper {
  width: 100%;
  overflow: hidden;
  position: relative;
}

.gallery-track {
  display: flex;
  width: 300%;
}

.gallery-group {
  width: 100%;
  display: flex;
  justify-content: space-between;
}

.image {
  width: 30%;
  border-radius: 6px;
}

/* ---------- стрелки как в макете ---------- */

.arrow {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  font-size: 45px;
  background: none;
  border: none;
  color: var(--color-bg-light);
  cursor: pointer;
  padding: 10px;
  opacity: 0.7;
  transition: 0.3s;
}

.arrow:hover {
  color: var(--color-orange);
  opacity: 1;
}

.arrow-left {
  left: -250px; /* выносим стрелку левее */
}

.arrow-right {
  right: -250px; /* выносим стрелку правее */
}

/* ---------- нижний ползунок ---------- */

.slider-bar {
  margin-top: 15px;
  height: 6px;
  background: #bbb;
  position: relative;
  border-radius: 3px;
  cursor: pointer;
}

.slider-thumb {
  width: 60px;
  height: 6px;
  background: orange;
  position: absolute;
  top: 0;
  border-radius: 3px;
  transition: left 0.4s ease;
}
</style>