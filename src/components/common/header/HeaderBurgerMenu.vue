<script setup>
import { ref, watch } from 'vue';
import { useScrollLock } from '@vueuse/core';
import CatButton from "../../ui/CatButton.vue";
import HeaderLogo from "./HeaderLogo.vue";
import WalletBalance from "./WalletBalance.vue";
import WalletSelect from "./WalletSelect.vue";

const isOpen = ref(false);

// Lock body scroll when menu is open
const body = ref(document.querySelector('body'));
const isLocked = useScrollLock(body);

watch(isOpen, (value) => {
  isLocked.value = value;
});

function closeMenu() {
  isOpen.value = false;
}
</script>

<template>
  <div class="md:hidden">
    <!-- Burger Icon -->
    <cat-button @click="isOpen = true" class="!p-2">
      <img src="/burger.svg" alt="Open menu" />
    </cat-button>

    <!-- Overlay -->
    <teleport to="body">
      <transition
        enter-active-class="transition ease-out duration-200"
        enter-from-class="opacity-0"
        enter-to-class="opacity-100"
        leave-active-class="transition ease-in duration-200"
        leave-from-class="opacity-100"
        leave-to-class="opacity-0"
      >
        <div v-if="isOpen" class="fixed inset-0 bg-bg z-50 p-0">
          <!-- Menu Header -->
          <div class="main-container flex items-center justify-between h-[54px] md:h-[86px]">
            <!-- You can place your logo here -->
            <header-logo />
            <cat-button @click="closeMenu" class="!p-2">
              <!-- Close Icon (X) -->
              <img src="/close-x.svg" alt="close">
            </cat-button>
          </div>

          <!-- Menu Navigation -->
          <nav class="space-y-8 p-4">
            <wallet-balance />
            <wallet-select @select="closeMenu" />
          </nav>
        </div>
      </transition>
    </teleport>
  </div>
</template>
