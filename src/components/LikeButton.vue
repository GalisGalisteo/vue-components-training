<script setup>
import { computed } from "@vue/reactivity";
import { ref } from "vue";

const likes = ref(0);
const bgColorArray = ["purple", "blue", "green", "yellow", "orange", "red"];
</script>

<template>
  <button
    @click="likes++"
    :class="`bg-[${bgColorArray[likes % bgColorArray.length]}]`"
    class="p-3 px-6 rounded text-white"
  >
    {{ likes }} likes
  </button>
</template>

<style lang="scss" scoped></style>
