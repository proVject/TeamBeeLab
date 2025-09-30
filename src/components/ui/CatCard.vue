<script setup>

</script>

<template>
  <article class="card flex- flex-col"><slot /></article>
</template>

<style scoped>
.card{
  border-radius: var(--border-radius);
  border: 1px solid var(--border-color);
  padding: 40px 32px;
}

@media screen and (max-width: 48rem) {
  .card{
    padding: 24px 0;
  }
}
</style>