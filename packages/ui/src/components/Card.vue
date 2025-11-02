<template>
  <div class="storybook-card">
    <slot></slot>
  </div>
</template>

<script lang="ts" setup>
  defineOptions({
    name: 'UiCard',
  });
</script>

<style scoped>
.storybook-card {
  border: 1px solid #eee;
  border-radius: 8px;
  padding: 20px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}
</style>
