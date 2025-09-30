<script setup>

</script>

<template>
  <!--  throw all native btn params with $attrs binding -->
  <button
      v-bind="$attrs"
      class="btn bg-bg text-text rounded-full inter-font hover:bg-card transition~">
    <slot/>
  </button>
</template>

<style scoped>
.btn {
  border: 1px solid #F4F4F4;
  box-shadow: var(--shadow);
  cursor: pointer;
  padding: 17px 32px;
  text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
  font-weight: 500;
  font-size: 24px;
  line-height: 16px;
  color: #383838
}

.btn:hover {
  background: var(--card-color);
}

@media screen and (max-width: 48rem) {
  .btn {
    font-size: 16px;
  }
}
</style>