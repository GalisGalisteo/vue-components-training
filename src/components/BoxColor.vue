<script setup>
import { computed } from "@vue/reactivity";

const props = defineProps(["r", "g", "b"]);

const rgbToHex = computed(() => {
  const componentToHex = (c) => {
    const hex = c.toString(16);
    return hex.length === 1 ? "0" + hex : hex;
  };

  const red = componentToHex(props.r);
  const green = componentToHex(props.g);
  const blue = componentToHex(props.b);

  return "#" + red + green + blue;
});

const whiteOrBlack = computed(() => {
  if (props.r < 128 || props.g < 128 || props.b < 128) {
    return "white";
  }

  return "black";
});

// const componentToHex = (c) => {
//   var hex = c.toString(16);
//   return hex.length == 1 ? "0" + hex : hex;
// }

// const rgbToHex = (r, g, b) =>  {
//   return "#" + componentToHex(r) + componentToHex(g) + componentToHex(b);
// }
//
</script>

<template>
  <div
    :style="{ backgroundColor: `rgb(${r}, ${g}, ${b})` }"
    class="flex flex-col rounded-xl p-5 shadow-xl h-20 w-80 items-center"
  >
    <p :class="`text-[${whiteOrBlack}]`">rgb({{ r }}, {{ g }}, {{ b }})</p>
    <p :class="`text-[${whiteOrBlack}]`">{{ rgbToHex }}</p>
  </div>
</template>

<style lang="scss" scoped></style>
