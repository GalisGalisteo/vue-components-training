<script setup>
defineProps(["lastName", "firstName", "gender", "height", "birth", "picture"]);
</script>

<template>
  <div class="flex rounded-xl p-5 shadow-xl bg-white">
    <div class="mr-5">
      <img class="rounded" :src="picture" :alt="`${firstName} ${lastName}`" />
    </div>
    <div class="text-gray-800">
      <p><strong>First Name:</strong> {{ firstName }}</p>
      <p><strong>Last Name:</strong> {{ lastName }}</p>
      <p><strong>Gender:</strong> {{ gender }}</p>
      <p><strong>Height:</strong> {{ (height / 100).toFixed(2) }} m</p>
      <p><strong>Birth:</strong> {{ birth.toDateString() }}</p>
    </div>
  </div>
</template>

<style scoped>

</style>
