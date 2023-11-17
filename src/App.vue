<script setup>
import BoxColor from "./components/BoxColor.vue";
import Carousel from "./components/Carousel.vue";
import ClickablePicture from "./components/ClickablePicture.vue";
import CreditCard from "./components/CreditCard.vue";
import Dice from "./components/Dice.vue";
import DriverCard from "./components/DriverCard.vue";
import Greetings from "./components/Greetings.vue";
import IdCard from "./components/IdCard.vue";
import LikeButton from "./components/LikeButton.vue";
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
      <BoxColor :r="128" :g="255" :b="200" />
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
    <section class="flex flex-col flex-wrap gap-4">
      <h2 class="text-xl font-bold text-blue-700">Greetings</h2>
      <div class="flex flex-wrap gap-4">
        <Greetings lang="de"
          ><span style="color: yellow">Ludwig</span></Greetings
        >
        <Greetings lang="fr"><strong>François</strong></Greetings>
      </div>
    </section>
    <section class="flex flex-col gap-4">
      <h2 class="text-xl font-bold text-blue-700">Rating</h2>
      <div class="grid grid-cols-3 justify-center gap-4">
        <Rating class="rounded-xl p-5 shadow-xl bg-white" :rate="0" />
        <Rating class="rounded-xl p-5 shadow-xl bg-white" :rate="1.49" />
        <Rating class="rounded-xl p-5 shadow-xl bg-white" :rate="1.5" />
        <Rating class="rounded-xl p-5 shadow-xl bg-white" :rate="3" />
        <Rating class="rounded-xl p-5 shadow-xl bg-white" :rate="4" />
        <Rating class="rounded-xl p-5 shadow-xl bg-white" :rate="5" />
      </div>
    </section>
    <section class="flex flex-col gap-4">
      <h2 class="text-xl font-bold text-blue-700">DriverCard</h2>
      <DriverCard
        name="Travis Kalanick"
        :rating="4.2"
        img="https://si.wsj.net/public/resources/images/BN-TY647_37gql_OR_20170621052140.jpg?width=620&height=428"
        :car="{ model: 'Toyota Corolla Altis', licensePlate: 'CO42DE' }"
      />
      <DriverCard
        name="Dara Khosrowshahi"
        :rating="4.9"
        img="https://ubernewsroomapi.10upcdn.com/wp-content/uploads/2017/09/Dara_ELT_Newsroom_1000px.jpg"
        :car="{ model: 'Audi A3', licensePlate: 'BE33ER' }"
      />
    </section>
    <section class="flex flex-col gap-4">
      <h2 class="text-xl font-bold text-blue-700">LikeButton</h2>
      <div class="flex flex-wrap gap-4">
        <LikeButton />
        <LikeButton />
      </div>
    </section>
    <section class="flex flex-col gap-4">
      <h2 class="text-xl font-bold text-blue-700">ClickablePicture</h2>
      <div class="flex flex-wrap gap-4">
        <ClickablePicture img="maxence.png" img-clicked="maxence-glasses.png" />
        <ClickablePicture img="maxence.png" img-clicked="maxence-glasses.png" />
      </div>
    </section>
    <section class="flex flex-col gap-4">
      <h2 class="text-xl font-bold text-blue-700">Dice</h2>
      <div class="flex gap-4">
        <Dice />
        <Dice />
      </div>
    </section>
    <section class="flex flex-col gap-4">
      <h2 class="text-xl font-bold text-blue-700">Carousel</h2>
      <div class="flex flex-wrap gap-4">
        <Carousel
          :images="[
            'https://randomuser.me/api/portraits/women/1.jpg',
            'https://randomuser.me/api/portraits/men/1.jpg',
            'https://randomuser.me/api/portraits/women/2.jpg',
            'https://randomuser.me/api/portraits/men/2.jpg',
          ]"
        />
      </div>
    </section>
  </div>
</template>

<style scoped></style>
