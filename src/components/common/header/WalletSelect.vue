<script setup>
import { ref } from 'vue';
import CatSelect from "../../ui/CatSelect.vue";

const options = ['0x63...B492', '0x12...CDEF', '0x78...GHIJ'];
const selectedWallet = ref(options[0]);
</script>

<template>
  <CatSelect @select="$emit('select', $event)" :options="options" v-model="selectedWallet">
    <template #trigger="{ attributes, value, isOpen }">
      <div
        v-bind="attributes"
        class="h-full flex gap-2 bg-card border border-border rounded-full px-6 py-2 items-center gap-2.5 cursor-pointer"
      >
        <span>{{ value }}</span>
        <!-- Placeholder for dropdown icon -->
        <span class="text-xs" :class="isOpen && 'rotate-180 transition-all duration-300'">▼</span>
      </div>
    </template>

    <template #option="option">
      <div class="py-2 px-4">
        {{ option.option }}
      </div>
    </template>
  </CatSelect>
</template>
