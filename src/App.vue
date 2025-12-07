<template>
  <div>Hello World!</div>
  <Gallery :images="photos" />
</template>

<style scoped>
div {
  font-family: var(--font-main);
}
</style>

<script setup lang="ts">
  import { ref } from "vue";
  import Gallery from "./components/Gallery.vue";

  const photos = ref([
    "images/uzbek1.png",
    "images/uzbek2.png",
    "images/uzbek3.png",
    "images/uzbek4.png",
    "images/uzbek5.png",
    "images/uzbek6.png",
    "images/uzbek7.png",
    "images/uzbek8.png",
    "images/uzbek9.png",
  ]);
</script>
