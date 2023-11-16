<script setup>
import { computed } from '@vue/reactivity';

const props = defineProps(["rate"]);

const rating = computed(() => {
  const rate = props.rate.toFixed(0);
  const outputRate = ["★".repeat(rate), "☆".repeat(5 - rate)];
  return outputRate.join("");
});

</script>

<template>
  <div>
    <p>{{rating}}</p>
  </div>
</template>

<style lang="scss" scoped></style>