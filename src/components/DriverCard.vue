<script setup>
import Rating from "./Rating.vue";

const props = defineProps(["name", "rating", "img", "car"]);
</script>

<template>
  <div class="rounded-xl p-5 shadow-xl bg-blue-600 text-white flex gap-4 w-96">
    <img :src="img" alt="" class="h-24 w-24 object-cover rounded-full" />
    <div class="flex flex-col justify-center">
        <div>{{ name }}</div>
        <Rating :rate="rating" />
        <div>{{ car.model }} - {{ car.licensePlate }}</div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
