<template>
  <div>Hello World!</div>
  <div class="first-block">
    <div class="header">

    </div>
    <div class="middle-content">

    </div>
    <div class="footer">
      
    </div>
  </div>
  <div class="second-block">
    <Description/>
    <Description_icons/>
    <div class="gallery">
      <Gallery1 :images="photos1" />
      <Gallery2 :images="photos2" />
    </div>
  </div>
</template>

<style scoped>
</style>

<script setup lang="ts">
  import { ref } from "vue";
  import Gallery1 from "./components/Gallery1.vue";
  import Gallery2 from "./components/Gallery2.vue";
  import Description from "./components/Description.vue";
  import Description_icons from "./components/Description_icons.vue";

  const photos1 = ref([
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
  const photos2 = ref([
    "images/gym1.jpg",
    "images/gym2.jpg",
    "images/gym3.jpg",
    "images/gym4.jpg",
    "images/gym5.jpg",
    "images/gym6.jpg",
    "images/gym7.jpg",
    "images/gym8.jpg",
    "images/gym9.jpg",
  ]);
</script>
