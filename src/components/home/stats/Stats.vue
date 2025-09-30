<template>
  <div class="flex lg:flex-row flex-col gap-5 justify-between px-4 md:px-0 pb-6 md:pb-8">
    <general-statistic :general="general" />
    <statistic-details :details="details" />
  </div>
</template>

<script setup>
import GeneralStatistic from "./GeneralStatistic.vue";
import StatisticDetails from "./StatisticDetails.vue";
import {ref} from "vue";

const coinTicker = ref('BIN')

const general = ref({
  amount: 25,
  coinTicker: coinTicker.value,
  maxRate: 200,
  icon: 'bin.svg',
})
const details = ref({
  rebonded: 10,
  coinTicker: coinTicker.value,
  sell: 360,
  marked: 7660,
})
</script>

<style>
</style>
