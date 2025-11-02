<template>
  <div class="storybook-input">
    <label :for="id">{{ label }}</label>
    <input :id="id" :type="type" :value="modelValue" @input="onInput" />
  </div>
</template>

<script lang="ts" setup>
import { defineProps, defineEmits } from 'vue';

const props = withDefaults(
  defineProps<{
    id: string;
    label: string;
    modelValue: string;
    type?: string;
  }>(),
  {
    type: 'text',
  }
);

const emit = defineEmits<{
  (e: 'update:modelValue', value: string): void;
}>();

const onInput = (event: Event) => {
  emit('update:modelValue', (event.target as HTMLInputElement).value);
};
</script>

<style scoped>
.storybook-input {
  display: flex;
  flex-direction: column;
}

.storybook-input label {
  margin-bottom: 8px;
  font-family: 'Nunito Sans', 'Helvetica Neue', Helvetica, Arial, sans-serif;
  font-size: 14px;
  color: #333;
}

.storybook-input input {
  border: 1px solid #eee;
  border-radius: 4px;
  padding: 10px;
  font-size: 14px;
}
</style>
