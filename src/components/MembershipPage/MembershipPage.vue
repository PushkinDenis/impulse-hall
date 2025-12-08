<template>
  <div class="third-block">
    <MembershipTable1/>
    <MembershipTable2/>
  </div>
</template>

<style scoped>
  .third-block {
    display: flex;
    flex-direction: column;
    height: 100vh;
    background: white;
  }
</style>

<script setup lang="ts">
  import MembershipTable1 from './Layout/MembershipTable1.vue';
  import MembershipTable2 from './Layout/MembershipTable2.vue';
</script>