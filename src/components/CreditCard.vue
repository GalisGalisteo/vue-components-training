<script setup>
defineProps([
  "type",
  "number",
  "expirationMonth",
  "expirationYear",
  "bank",
  "owner",
  "bgColor",
  "color",
]);
</script>

<template>
  <div
    :class="`bg-[${bgColor}]`"
    class="rounded-xl p-6 shadow-xl w-96 h-48 flex flex-col justify-between gap-4"
  >
    <div class="flex justify-end">
      <img
        v-if="type === 'Visa'"
        class="w-20"
        src="../assets/images/visa.png"
        alt=""
      />
      <img
        v-else-if="type === 'Master Card'"
        class="w-12"
        src="../assets/images/master-card.svg"
        alt=""
      />
    </div>
    <div class="flex justify-center gap-3">
      <div class="flex items-center gap-1">
        <div :class="`bg-[${color}]`" class="h-3 w-3 rounded-full"></div>
        <div :class="`bg-[${color}]`" class="h-3 w-3 rounded-full"></div>
        <div :class="`bg-[${color}]`" class="h-3 w-3 rounded-full"></div>
        <div :class="`bg-[${color}]`" class="h-3 w-3 rounded-full"></div>
      </div>
      <div class="flex items-center gap-1">
        <div :class="`bg-[${color}]`" class="h-3 w-3 rounded-full"></div>
        <div :class="`bg-[${color}]`" class="h-3 w-3 rounded-full"></div>
        <div :class="`bg-[${color}]`" class="h-3 w-3 rounded-full"></div>
        <div :class="`bg-[${color}]`" class="h-3 w-3 rounded-full"></div>
      </div>
      <div class="flex items-center gap-1">
        <div :class="`bg-[${color}]`" class="h-3 w-3 rounded-full"></div>
        <div :class="`bg-[${color}]`" class="h-3 w-3 rounded-full"></div>
        <div :class="`bg-[${color}]`" class="h-3 w-3 rounded-full"></div>
        <div :class="`bg-[${color}]`" class="h-3 w-3 rounded-full"></div>
      </div>
      <div :class="`text-[${color}]`" class="text-4xl">{{ number.slice(-4) }}</div>
    </div>
    <div>
      <div  :class="`text-[${color}]`" class="flex gap-8">
        <div>
          Expires: {{ expirationMonth.toString().padStart(2, "0") }}/{{
            expirationYear.toString().slice(-2)
          }}
        </div>
        <div>{{ bank }}</div>
      </div>
      <div  :class="`text-[${color}]`" >{{ owner }}</div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
