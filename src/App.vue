<template>
  <div id="app" class="min-h-screen flex flex-col relative">
    <cat-header/>
    <main class="flex-1">
      <Hero/>
      <section class="main-container">
        <div class="pt-8 md:pt-10 pb-15 md:pb-18">
          <cat-card class="max-w-204 mx-auto">
            <stats/>
            <staking-table/>
          </cat-card>
        </div>
      </section>
    </main>
    <cat-footer/>
  </div>
</template>

<script setup>
import CatHeader from './components/common/header/CatHeader.vue';
import Hero from './components/home/Hero.vue';
import Stats from './components/home/stats/Stats.vue';
import StakingTable from './components/home/staking/StakingTable.vue';
import CatFooter from './components/common/CatFooter.vue';
import CatCard from "./components/ui/CatCard.vue";
</script>
