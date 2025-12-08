<template>
  <div class="cont" :class="[variant, color]">
    <button class="btn" @click="$emit('click')">
      <span class="content">
        <slot>Кнопка</slot>
      </span>
    </button>
  </div>
</template>

<script setup lang="ts">
defineProps({
  variant: {
    type: String as () => 'regular' | 'custom',
    default: 'regular',
  },
  color: {
    type: String as () => 'regular' | 'orange',
    default: 'regular',
  },
});

defineOptions({ name: 'AppButton' });
</script>

<style scoped>
.cont {
  position: relative;
  display: inline-block;
  max-width: fit-content;
}

.cont.custom::before {
  content: '';
  position: absolute;
  top: 8px;
  left: -12px;
  right: 12px;
  bottom: -8px;
  background: var(--color-orange);
  transform: skew(-25deg);
  z-index: 0;
  pointer-events: none;
}

.btn {
  position: relative;
  z-index: 1;
  background: transparent;
  padding: 20px 30px;
  cursor: pointer;
  transform: skew(-25deg);
  display: inline-block;
  border: 1px solid var(--color-bg-light, #fff);
  color: var(--color-bg-light, #fff);
}

.cont.orange .btn {
  color: var(--color-orange, #ff7a00);
  border-color: var(--color-orange, #ff7a00);
}

.cont.orange .btn:hover,
.cont.orange .btn:active,
.cont.orange .btn:focus {
  background: var(--color-orange, #ff7a00);
  color: var(--color-bg-light, #fff);
}

.content {
  display: inline-block;
  position: relative;
  z-index: 2;
  transform: skew(25deg);
  font-weight: var(--font-bold);
}
</style>
