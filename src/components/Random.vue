<script setup>
import { computed } from '@vue/reactivity';

const props = defineProps(["min", "max"]);

const randomNumber = computed(() => {
  return Math.floor(Math.random() * (props.max - props.min + 1) + props.min);
});
</script>

<template>
  <div class="rounded-xl p-5 shadow-xl bg-white">
    <p>
      Random value between {{ min }} and {{ max }} =>
      {{ randomNumber }}
    </p>
  </div>
</template>

<style lang="scss" scoped></style>
