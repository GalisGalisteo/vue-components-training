<script setup>
import { ref } from 'vue';

const isClicked = ref(false);
</script>
<template>
  <img
    @click="isClicked = !isClicked"
    class="h-40"
    :src="
      isClicked
        ? '../../public/maxence-glasses.png'
        : '../../public/maxence.png'
    "
    alt="boy"
  />
</template>

<style lang="scss" scoped></style>
