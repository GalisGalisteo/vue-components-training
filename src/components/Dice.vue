<script setup>
import { ref } from "vue";

const randomDice = () => {
  const diceNumber = Math.floor(Math.random() * 6) + 1;
  return `src/assets/images/dice${diceNumber}.png`;
};

const dice = ref(randomDice());

const handleClick = () => {
  dice.value = "src/assets/images/dice-empty.png";
  setTimeout(() => (dice.value = randomDice()), 1000);
};
</script>

<template>
  <img @click="handleClick" class="w-32" :src="dice" alt="" />
</template>

<style lang="scss" scoped></style>
