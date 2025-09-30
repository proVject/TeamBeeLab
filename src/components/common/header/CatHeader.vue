<template>
    <header class="bg-bg sticky top-0 z-1">
    <nav class="main-container flex items-center justify-between h-[54px] md:h-[86px]">
      <!-- Logo -->
      <header-logo />
      <div>
        <!-- burger menu mob -->
        <header-burger-menu />
        <!-- Wallet Info -->
        <div class="hidden md:flex gap-4">
          <wallet-balance />
          <wallet-select />
        </div>
      </div>
    </nav>
  </header>
</template>

<script setup>
import HeaderLogo from "./HeaderLogo.vue";
import HeaderBurgerMenu from "./HeaderBurgerMenu.vue";
import WalletBalance from "./WalletBalance.vue";
import WalletSelect from "./WalletSelect.vue";
</script>
