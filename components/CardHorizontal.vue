<template>
  <NuxtLink
    to=""
    class="card group mb-6 flex max-w-lg basis-1/3 items-center justify-center overflow-hidden rounded-2xl border bg-white hover:bg-slate-50"
  >
    <div
      class="basis-1/3 overflow-hidden bg-pink-200 object-cover duration-1000 ease-out group-hover:scale-105"
    >
      <img
        class="min-h-[80px] w-full object-cover"
        :src="img"
        alt=""
      />
      <!-- src="~/assets/img/card3pcs/1.png" -->
    </div>
    <div class="basis-2/3 pl-3 text-lg font-semibold">
      <h1>{{ name }}</h1>
    </div>
  </NuxtLink>
</template>

<script setup>
const props = defineProps({
  name: String,
  category: String,
  description: String,
  img: String,
  price: Number,
});
</script>
