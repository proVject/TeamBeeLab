<script setup>
import {computed} from "vue";

const props = defineProps({
  general: {type: Object, required: true},
})

const iconUrl = computed(() => {
  return `${import.meta.env.BASE_URL}/coins/${props.general.icon}`
})
</script>

<template>
  <div class="flex flex-col">
    <p class="all-title text-black/50 mb-3">Всього застекано</p>
    <div class="flex mb-3.5 gap-2 items-center">
      <img
          class="flex"
          :src="iconUrl" :alt="general.coinTicker"
      />
      <span class="amount">{{ general.amount }} {{ general.coinTicker }}</span>
    </div>
    <div class="flex gap-3 items-center">
      <img src="/warning.svg" alt="warn" />
      <span class="text-black/50 max-rate">Максимальний дохід по стекінгу {{general.maxRate}}%</span>
    </div>
  </div>
</template>

<style scoped>
.all-title {
  font-weight: 500;
  font-size: 14px;
  line-height: 20px;
}
.amount{
  font-weight: 700;
  font-size: 52px;
  line-height: 62px;
}
.max-rate{
  font-size: 12px;
  line-height: 150%;
}

@media screen and (max-width: 48rem) {
  .amount{
    font-weight: 700;
    font-size: 38px;
    line-height: 48px;
  }
}
</style>