<script setup>
defineProps({
  details: { type: Object, required: true },
})
</script>

<template>
  <div class="flex flex-col lg:max-w-[423px] w-full">
    <div class="flex border-b-1 border-b-border px-0 md:px-4 py-2.5 justify-between items-center">
      <span>Ребондіровано</span>
      <span>{{ details.rebonded }} {{ details.coinTicker }}</span>
    </div>
    <div class="flex border-b-1 border-b-border px-0 md:px-4 py-2.5 justify-between items-center">
      <span>Продано BIN</span>
      <span>{{ details.sell }} {{ details.coinTicker }}</span>
    </div>
    <div class="flex w-full border-b-border px-0 md:px-4 py-2.5 justify-between items-center">
      <span>Заклеймено BIN</span>
      <span>{{ details.marked }} {{ details.coinTicker }}</span>
    </div>
  </div>
</template>

<style scoped>

</style>