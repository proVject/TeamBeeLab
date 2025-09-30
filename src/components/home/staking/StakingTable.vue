<template>
  <!-- mob version -->
  <div class="md:hidden flex flex-col border-t-1 border-t-border">
    <staking-card v-for="(item, index) in stakingItems" :key="index" :item="item" :coinTicker="coinTicker" />
  </div>

  <!-- desktop version -->
  <CatTable
    :data="stakingItems"
    :columns="STAKING_COLUMNS"
    class="hidden md:table"
  >
    <template #default="{ row, column }">
      <span v-if="column.prop === 'days'">{{ row.days }} Днів</span>
      <span v-if="column.prop === 'earnPerDay'">{{ row.earnPerDay }}%</span>
      <span v-if="column.prop === 'earnPerPeriod'">{{ row.earnPerPeriod }}%</span>
      <span v-if="column.prop === 'waiting'">{{ row.waiting }} {{ coinTicker }}</span>
      <div
          v-if="column.prop === 'status'"
          class="rounded-lg p-2.5 font-bold w-fit"
          :class="row.status === 'active'
            ? 'bg-success-light text-success'
            : 'bg-error-light text-error'
          "
      >
        {{ row.status === 'active' ? 'Активний' : 'Неактивний' }}
      </div>
    </template>
  </CatTable>
</template>

<script setup>
import { ref } from "vue";
import { STAKING_COLUMNS } from "../../../constants/staking.js";
import CatTable from "../../ui/CatTable.vue";
import StakingCard from "./StakingCard.vue";

const coinTicker = ref('BIN')

const stakingItems = ref([
  {
    days: 17,
    earnPerDay: 0.5,
    earnPerPeriod: 31.7,
    waiting: 10,
    status: 'active'
  },
  {
    days: 17,
    earnPerDay: 0.5,
    earnPerPeriod: 31.7,
    waiting: 10,
    status: 'inactive'
  },
  {
    days: 17,
    earnPerDay: 0.5,
    earnPerPeriod: 31.7,
    waiting: 10,
    status: 'active'
  },
]);
</script>