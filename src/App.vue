<script setup>
import BoxColor from "./components/BoxColor.vue";
import CreditCard from "./components/CreditCard.vue";
import Greetings from "./components/Greetings.vue";
import IdCard from "./components/IdCard.vue";
import Random from "./components/Random.vue";
import Rating from "./components/Rating.vue";
</script>

<template>
  <div class="flex flex-col items-center gap-10 my-8">
    <h1 class="text-3xl font-bold">Creación de componentes con Vue</h1>
    <section class="flex flex-col gap-4">
      <h2 class="text-xl font-bold text-blue-700">Id Card</h2>
      <IdCard
        last-name="Doe"
        first-name="John"
        gender="male"
        :height="178"
        :birth="new Date('1992-07-14')"
        picture="https://randomuser.me/api/portraits/men/44.jpg"
      />
      <IdCard
        last-name="Delores "
        first-name="Obrien"
        gender="female"
        :height="172"
        :birth="new Date('1988-05-11')"
        picture="https://randomuser.me/api/portraits/women/44.jpg"
      />
    </section>
    <section class="flex flex-col gap-4">
      <h2 class="text-xl font-bold text-blue-700">Random</h2>
      <Random :min="1" :max="6" />
      <Random :min="1" :max="100" />
    </section>
    <section class="flex flex-col gap-4">
      <h2 class="text-xl font-bold text-blue-700">BoxColor</h2>
      <BoxColor :r="255" :g="0" :b="0" />
      <BoxColor :r="128" :g="255" :b="0" />
    </section>
    <section class="flex flex-col gap-4">
      <h2 class="text-xl font-bold text-blue-700">CreditCard</h2>
      <CreditCard
        type="Visa"
        number="0123456789018845"
        :expiration-month="3"
        :expiration-year="2021"
        bank="BNP"
        owner="Maxence Bouret"
        bg-color="#11aa99"
        color="white"
      />
      <CreditCard
        type="Master Card"
        number="0123456789010995"
        :expiration-month="3"
        :expiration-year="2021"
        bank="N26"
        owner="Maxence Bouret"
        bg-color="#eeeeee"
        color="#222222"
      />
      <CreditCard
        type="Visa"
        number="0123456789016984"
        :expiration-month="12"
        :expiration-year="2019"
        bank="Name of the Bank"
        owner="Firstname Lastname"
        bg-color="#ddbb55"
        color="white"
      />
    </section>
    <section class="flex flex-col gap-4">
      <h2 class="text-xl font-bold text-blue-700">Greetings</h2>
      <Greetings lang="de"><span style="color: yellow">Ludwig</span></Greetings>
      <Greetings lang="fr"><strong>François</strong></Greetings>
    </section>
    <section class="flex flex-col gap-4">
      <Rating :rate="0" />
      <Rating :rate="1.49" />
      <Rating :rate="1.5" />
      <Rating :rate="3" />
      <Rating :rate="4" />
      <Rating :rate="5" />
    </section>
  </div>
</template>

<style scoped></style>
