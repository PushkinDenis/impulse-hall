<template>
  <div class="third-block">
    <MembershipTable1/>
    <MembershipTable2/>
    <MembershipBlocks/>
  </div>
</template>

<style scoped>
  .third-block {
    display: flex;
    flex-direction: column;
    height: 120vh;
    background: white;
    color: var(--color-bg);
  }
</style>

<script setup lang="ts">
  import MembershipTable1 from './Layout/MembershipTable1.vue';
  import MembershipTable2 from './Layout/MembershipTable2.vue';
  import MembershipBlocks from './Layout/MembershipBlocks.vue';
</script>