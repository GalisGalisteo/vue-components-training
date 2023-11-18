<script setup>
const props = defineProps(["limit"]);
</script>

<template>
    <div class="flex flex-wrap">
      <div
        v-for="(l, i) in limit"
        :class="i % 2 ? 'bg-red-600' : 'bg-white'"
        class="w-24 h-24 text-3xl flex items-center justify-center border shadow-md border-black"
      >
        <div>{{ i + 1 }}</div>
      </div>
    </div>
</template>

<style lang="scss" scoped></style>
