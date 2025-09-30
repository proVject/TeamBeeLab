<script setup>
import { ref } from 'vue';
import { onClickOutside } from '@vueuse/core';

const props = defineProps({
  options: {
    type: Array,
    required: true,
  },
  modelValue: {
    type: [String, Object, Number],
    default: null,
  },
});

const emit = defineEmits(['update:modelValue', 'select']);

const isOpen = ref(false);
const selectRef = ref(null);

// Close dropdown when clicking outside
onClickOutside(selectRef, () => {
  isOpen.value = false;
});

function selectOption(option) {
  emit('update:modelValue', option);
  emit('select', option);
  isOpen.value = false;
}

function toggleDropdown() {
  isOpen.value = !isOpen.value;
}
</script>

<template>
  <div class="relative" ref="selectRef">
    <!-- Trigger -->
    <div @click="toggleDropdown" class="h-full cursor-pointer">
      <slot name="trigger" :value="modelValue" :isOpen="isOpen">
        <!-- Default fallback trigger -->
        <button class="border p-2 rounded flex justify-between items-center w-full">
          <span>{{ modelValue }}</span>
          <span>▼</span>
        </button>
      </slot>
    </div>

    <!-- Dropdown Menu -->
    <transition
      enter-active-class="transition ease-out duration-100"
      enter-from-class="transform opacity-0 scale-95"
      enter-to-class="transform opacity-100 scale-100"
      leave-active-class="transition ease-in duration-75"
      leave-from-class="transform opacity-100 scale-100"
      leave-to-class="transform opacity-0 scale-95"
    >
      <div
        v-if="isOpen"
        class="absolute z-10 top-full left-0 mt-2 w-full cat-select-dropdown"
      >
        <ul>
          <li
            v-for="(option, index) in options"
            :key="index"
            @click="selectOption(option)"
            class="cat-select-option"
          >
            <slot name="option" :option="option">
              <!-- Default fallback option -->
              <div class="py-2 px-4">
                {{ option.label || option }}
              </div>
            </slot>
          </li>
        </ul>
      </div>
    </transition>
  </div>
</template>

<style>
.cat-select-dropdown {
  border-radius: var(--border-radius);
  border: 1px solid var(--border-color);
  background: var(--card-color);
  box-shadow: var(--shadow);
  overflow: hidden;
}

.cat-select-option {
  cursor: pointer;
}

.cat-select-option:hover {
  background: var(--bg-color);
}
</style>