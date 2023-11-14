<script setup>
defineProps(["min", "max"]);

const randomNumber = (min, max) => {
  return Math.floor(Math.random() * (max - min + 1) + min);
};
</script>

<template>
  <div class="rounded-xl p-5 shadow-xl bg-white">
    <p>
      Random value between {{ min }} and {{ max }} =>
      {{ randomNumber(min, max) }}
    </p>
  </div>
</template>

<style lang="scss" scoped></style>
