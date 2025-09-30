<template>
  <div class="flex flex-col gap-4 text-[14px] border-b-1 border-b-border py-6 px-4">
    <staking-card-item :label="STAKING_COLUMNS[0].label">
      <template #default>
        {{ item.days }} днів
      </template>
    </staking-card-item>
    <staking-card-item :label="STAKING_COLUMNS[1].label">
      <template #default>
        {{ item.earnPerDay }}%
      </template>
    </staking-card-item>
    <staking-card-item :label="STAKING_COLUMNS[1].label">
      <template #default>
        <span>{{ item.earnPerDay }}%</span>
      </template>
    </staking-card-item>
    <staking-card-item :label="STAKING_COLUMNS[2].label">
      <template #default>
        <span>{{ item.earnPerPeriod }}%</span>
      </template>
    </staking-card-item>
    <staking-card-item :label="STAKING_COLUMNS[3].label" :value="item.waiting">
      <template #default>
        <span>{{ item.waiting }} {{ coinTicker }}</span>
      </template>
    </staking-card-item>
    <staking-card-item :label="STAKING_COLUMNS[4].label">
      <template #default>
        <div
            class="rounded-lg px-2.5 py-1.5 font-bold w-fit -mt-1"
            :class="item.status === 'active'
            ? 'bg-success-light text-success'
            : 'bg-error-light text-error'
          "
        >
          {{ item.status === 'active' ? 'Активний' : 'Неактивний' }}
        </div>
      </template>
    </staking-card-item>
  </div>
</template>

<script setup>
import {STAKING_COLUMNS} from "../../../constants/staking.js";
import StakingCardItem from "./StakingCardItem.vue";

defineProps({
  item: { type: Object, required: true },
  coinTicker: { type: String, required: true },
});
</script>
