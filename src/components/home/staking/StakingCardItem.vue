<template>
  <div class="flex justify-between items-center">
    <span class="text-secondary-text">{{ label }}</span>
    <slot>
      <span>{{ value }}</span>
    </slot>
  </div>
</template>

<script setup>
defineProps({
  label: {
    type: String,
    required: true,
  },
  value: {
    type: [String, Number],
    default: ''
  }
});
</script>
