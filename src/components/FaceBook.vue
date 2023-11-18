<script setup>
import profiles from "../data/berlin.json";
</script>

<template>
  <div v-for="p in profiles" class="flex rounded-xl p-5 shadow-xl bg-white w-96">
    <div class="mr-5 w-32">
      <img class="rounded" :src="p.img" :alt="`${p.firstName} ${p.lastName}`" />
    </div>
    <div class="text-gray-800 text-xl flex flex-col justify-center">
      <p><strong>First Name:</strong> {{ p.firstName }}</p>
      <p><strong>Last Name:</strong> {{ p.lastName }}</p>
      <p><strong>Country:</strong> {{ p.country }}</p>
      <p><strong>Type:</strong> {{ p.isStudent ? "Student" : "Teacher" }}</p>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
