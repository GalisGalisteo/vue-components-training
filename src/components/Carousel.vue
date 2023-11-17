<script setup>
import { ref } from "vue";

const props = defineProps(["images"]);

const index = ref(0);

const leftClick = () => {
  index.value--;
  if (index.value < 0) {
    index.value = props.images.length - 1;
  }
  props.images[index];
};

const rightClick = () => {
  index.value++;
  if (index.value > props.images.length - 1) {
    index.value = 0;
  }
  props.images[index];
};
</script>

<template>
  <div class="flex items-end gap-4">
    <button
      class="bg-gray-300 px-4 rounded border-2 border-gray-600 hover:bg-slate-600 hover:text-white border-l shadow-md active:scale-x-90"
      @click="leftClick"
    >
      Left
    </button>
    <img :src="images[index]" alt="" />
    <button
      class="bg-gray-300 px-4 rounded border-2 border-gray-600 hover:bg-slate-600 hover:text-white border-l shadow-md active:scale-x-90"
      @click="rightClick"
    >
      Right
    </button>
  </div>
</template>

<style lang="scss" scoped></style>
