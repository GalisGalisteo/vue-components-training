<script setup>
import { ref } from "vue";
import profiles from "../data/berlin.json";

const uniqueCountries = ref([]);
const limitCountries = ref(3);
const showMoreCountries = ref(3);

const countrySet = new Set(profiles.map((p) => p.country));
uniqueCountries.value = Array.from(countrySet).sort();

const countriesClicked = ref([]);

const handleClickCountry = (event) => {
  const clickedCountry = event.target.textContent;
  if (!countriesClicked.value.includes(clickedCountry)) {
    countriesClicked.value.push(clickedCountry);
  } else {
    countriesClicked.value = countriesClicked.value.filter(
      (c) => c !== clickedCountry
    );
  }
};
</script>

<template>
  <div class="flex flex-wrap gap-2 w-96">
    <div
      @click="limitCountries = uniqueCountries.length"
      class="bg-blue-600 text-white px-4 rounded border-2 border-gray-600 hover:bg-blue-400 hover:text-white border-l shadow-md active:scale-x-105"
    >
      All
    </div>
    <div
      @click="handleClickCountry"
      v-for="(country, i) in uniqueCountries"
      v-show="i < limitCountries"
      class="bg-blue-600 text-white px-4 rounded border-2 border-gray-600 hover:bg-blue-400 hover:text-white border-l shadow-md active:scale-x-105"
    >
      {{ country }}
    </div>
    <div
      v-if="limitCountries < uniqueCountries.length"
      v-show="limitCountries < uniqueCountries.length"
      @click="limitCountries += showMoreCountries"
      class="bg-blue-600 text-white px-4 rounded border-2 border-gray-600 hover:bg-blue-400 hover:text-white border-l shadow-md active:scale-x-105"
    >
      →
    </div>
    <div
      v-else
      v-show="limitCountries > 0"
      @click="limitCountries = showMoreCountries"
      class="bg-blue-600 text-white px-4 rounded border-2 border-gray-600 hover:bg-blue-400 hover:text-white border-l shadow-md active:scale-x-105"
    >
      ←
    </div>
  </div>

  <div
    v-for="p in profiles"
    :class="countriesClicked.includes(p.country) ? 'bg-blue-400' : 'bg-white'"
    class="flex rounded-xl p-5 shadow-xl w-96"
  >
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
