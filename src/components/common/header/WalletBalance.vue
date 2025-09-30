<script setup>
import {ref} from "vue";

const balance = ref(100)
const coinTicker = ref('BNB')
</script>

<template>
  <div class="bg-card border border-border border-1 rounded-full px-6 py-2 flex flex-col">
    <span class="font-[300] text-[14px]">Wallet balance: </span>
    <span class="font-[700]">{{ balance }} {{ coinTicker }}</span>
  </div>
</template>

<style scoped>

</style>