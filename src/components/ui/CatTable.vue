<template>
  <table class="w-full border-collapse">
    <thead>
      <tr class="border-b border-border">
        <th
          v-for="column in columns"
          :key="column.prop"
          class="text-left text-black/50 py-2.5 px-4 font-[400]"
        >
          {{ column.label }}
        </th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(row, rowIndex) in data" :key="rowIndex" class="border-b border-border">
        <td v-for="column in columns" :key="column.prop" class="py-2.5 px-4">
          <slot :row="row" :column="column">
            {{ row[column.prop] }}
          </slot>
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script setup>
defineProps({
  columns: {
    type: Array,
    required: true,
  },
  data: {
    type: Array,
    required: true,
  },
});
</script>
