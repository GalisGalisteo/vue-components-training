<script setup>
const props = defineProps(["lang"]);
</script>

<template>
  <div class="rounded-xl p-5 shadow-xl bg-white">
    <div v-if="lang === 'de'">Hallo <slot /></div>
    <div v-else-if="lang === 'fr'">Bonjour <slot /></div>
  </div>
</template>

<style lang="scss" scoped></style>
