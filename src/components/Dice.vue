<script setup>
import { ref } from "vue";

const randomDice = () => {
  const diceNumber = Math.floor(Math.random() * 6) + 1;
  return `src/assets/images/dice${diceNumber}.png`;
};

const dice = ref(randomDice());

const delay = (ms) => new Promise(resolve => setTimeout(resolve, ms));

const handleClick = async () => {
  for (let i = 0; i < 10; i++) {
    dice.value = "src/assets/images/dice-empty.png";
    await delay(100);
    dice.value = randomDice();
    await delay(100);
  }
};
</script>

<template>
  <img @click="handleClick" class="w-32" :src="dice" alt="" />
</template>

<style lang="scss" scoped></style>
