<template>
  <div class="second-block">
    <Description/>
    <Description_icons/>
    <div class="gallery">
      <Gallery1 :images="images1" />
      <Gallery2 :images="images2" />
    </div>
    <div class="rectangles">
      <img src="/images/rectangle1.png"></img>
      <img src="/images/rectangle2.png"></img>
    </div>
  </div>
</template>

<style scoped>
  .gallery {
    padding-bottom: 150px;
  }
  .rectangles {
    position: relative;

    > img {
      position: absolute;
      left: 0;
      bottom: 0;
      width: 160px;
    }

    > img:first-child {
      z-index: 10;
      width: 120px;
    }

    > img:last-child {
      z-index: 5;
    }
  }
</style>

<script setup lang="ts">
  import { ref } from "vue";
  import Gallery1 from "./page_components/Gallery1.vue";
  import Gallery2 from "./page_components/Gallery2.vue";
  import Description from "./page_components/Description.vue";
  import Description_icons from "./page_components/DescriptionIcons.vue";

  const images1 = ref([
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
  const images2 = ref([
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