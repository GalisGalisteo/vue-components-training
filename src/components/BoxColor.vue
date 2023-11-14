<script setup>
defineProps(["r", "g", "b"]);

const componentToHex = (c) => {
  var hex = c.toString(16);
  return hex.length == 1 ? "0" + hex : hex;
}

const rgbToHex = (r, g, b) =>  {
  return "#" + componentToHex(r) + componentToHex(g) + componentToHex(b);
}
</script>

<template>
  <div :style="{backgroundColor: `rgb(${ r }, ${ g }, ${ b })`}" class="flex flex-col rounded-xl p-5 shadow-xl h-20 w-80 items-center">
    <p class="text-white">rgb({{r}}, {{g}}, {{b}})</p>
    <p class="text-white">{{ rgbToHex(r, g, b) }}</p>
  </div>
</template>

<style lang="scss" scoped></style>
