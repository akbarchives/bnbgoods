<template>
  <NuxtLink
    to=""
    class="card group min-w-fit max-w-lg rounded-2xl border bg-white hover:bg-slate-100"
  >
    <!-- class="card flex basis-full flex-col overflow-hidden border border-pink-500 sm:basis-1/2 sm:pr-4 md:basis-1/3 lg:basis-1/4" -->
    <div class="group overflow-hidden rounded-t-2xl">
      <img
        class="aspect-square w-full overflow-hidden object-cover object-top duration-1000 ease-out group-hover:scale-105 sm:aspect-square"
        alt=""
        :src="img"
      />
    </div>
    <div class="p-4">
      <div class="flex flex-row justify-between">
        <h1
          class="line-clamp-1 basis-9/12 text-lg font-semibold sm:basis-3/4 lg:basis-9/12"
        >
          {{ title }}
        </h1>
        <h1 class="basis-3/12 sm:basis-1/4 lg:basis-3/12">
          <span class="text-base text-yellow-400">&#9733;</span> {{ rating }}
        </h1>
      </div>
      <NuxtLink
        to="/"
        class="font-medium text-slate-800 transition-all duration-200 hover:underline hover:ease-out"
      >
        {{ category ? category : 'category...' }}
      </NuxtLink>
      <h1 class="my-2 line-clamp-2 font-normal text-slate-600">
        {{ description ? description : 'description...' }}
      </h1>

      <!-- when have discount number -->
      <div v-if="discountPercentage">
        <h1 class="text-lg font-semibold">
          ${{ Math.floor(price - (price * discountPercentage) / 100) }}
          <span class="rounded-lg bg-red-600 px-1 text-white"
            >{{ Math.floor(discountPercentage) }}%</span
          >
        </h1>
        <h1 class="text-sm font-semibold text-slate-600 line-through">
          ${{ price ? price : '450' }}
        </h1>
      </div>
      <div v-else>
        <h1 class="text-lg font-semibold">${{ price ? price : '450' }}</h1>
      </div>
    </div>
  </NuxtLink>
</template>

<!-- <script setup>
const props = defineProps({
  name: String,
  category: String,
  description: String,
  img: String,
  price: Number,
  rating: Number,
});
</script> -->

<script>
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue';

// Import Swiper styles
import 'swiper/css';

import 'swiper/css/pagination';
import 'swiper/css/navigation';

// import './style.css';

// import required modules
import { Navigation, Pagination } from 'swiper';

export default {
  components: {
    Swiper,
    SwiperSlide,
  },

  props: {
    title: String,
    rating: Number,
    category: String,
    description: String,
    brand: String,
    price: Number,
    discountPercentage: Number,
    thumbnail: String,
    img: String,
    img1: String,
    img2: String,
    img3: String,
  },

  setup() {
    return {
      modules: [Navigation, Pagination],
    };
  },
};
</script>
<style>
.swiper-button-next::after,
.swiper-button-prev::after {
  transform: scale(0.4);
}
.swiper-button-next,
.swiper-button-prev {
  margin-top: -15px;
  color: black;
  /* transform: scale(0.5); */
  width: 30px;
  height: 30px;
  background: white;
  border-radius: 999px;
  border: 2px solid #a8a8a8;

  transition: all 0.2s ease-in-out;
}
.swiper-button-next:hover,
.swiper-button-prev:hover {
  /* transform: scale(0.6); */

  transition: all 0.2s ease-in-out;
}

.swiper-pagination-bullet-active {
  background-color: white !important;
}
.swiper-pagination-bullet {
  border: 1px solid #9e9e9e;
}

:root {
  --swiper-pagination-bullet-size: 12px;
  --swiper-pagination-bullet-height: 12px;
  /*
  --swiper-pagination-color: var(--swiper-theme-color);
  --swiper-pagination-bullet-width: 8px;
  --swiper-pagination-bullet-inactive-color: #000;
  --swiper-pagination-bullet-inactive-opacity: 0.2;
  --swiper-pagination-bullet-opacity: 1;
  --swiper-pagination-bullet-horizontal-gap: 4px;
  --swiper-pagination-bullet-vertical-gap: 6px;
  */
}
</style>
