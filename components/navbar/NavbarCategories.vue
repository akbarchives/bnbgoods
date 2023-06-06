<template>
  <nav class="select-none border-b-2 bg-white">
    <div class="mx-auto max-w-screen-2xl">
      <div class="h-20 px-6 sm:px-8">
        <!-- for sm screen -->
        <div
          class="flex w-full flex-row items-center justify-between self-end md:hidden"
        >
          <swiper
            :slidesPerView="5"
            :spaceBetween="30"
            :navigation="true"
            :modules="modules"
            class="mySwiper flex h-20 basis-auto flex-row items-end"
          >
            <swiper-slide
              class="flex flex-col justify-center border-b-[3px] border-transparent pt-4 text-center opacity-70 duration-200 hover:border-b-[3px] hover:border-black hover:opacity-100 hover:duration-200"
            >
              <nuxt-link
                :to="`/products`"
                class="py-1 text-sm font-medium text-black"
              >
                <img
                  class="mx-auto h-8 w-8"
                  src="~/assets/icons/category.svg"
                  alt=""
                />
                All Products</nuxt-link
              >
            </swiper-slide>
            <swiper-slide
              v-for="c in categories"
              class="flex flex-col justify-center border-b-[3px] border-transparent pt-4 text-center opacity-70 duration-200 hover:border-b-[3px] hover:border-black hover:opacity-100 hover:duration-200"
            >
              <nuxt-link
                :to="`/categories/${c}`"
                class="py-1 text-sm font-medium text-black"
              >
                <img
                  class="mx-auto h-8 w-8"
                  src="~/assets/icons/discount.svg"
                  alt=""
                />
                #{{ c }}</nuxt-link
              >
            </swiper-slide>
          </swiper>
          <!-- <ButtonFilter /> -->
        </div>
        <!-- for LG screen -->
        <div
          class="hidden w-full flex-row items-center justify-between self-end md:flex"
        >
          <swiper
            :slidesPerView="8"
            :spaceBetween="30"
            :navigation="true"
            :modules="modules"
            class="mySwiper flex h-20 basis-auto flex-row items-end"
          >
            <swiper-slide
              class="flex flex-col justify-center border-b-[3px] border-transparent pt-4 text-center opacity-70 duration-200 hover:border-b-[3px] hover:border-black hover:opacity-100 hover:duration-200"
            >
              <nuxt-link
                :to="`/products`"
                class="py-1 text-sm font-medium text-black"
              >
                <img
                  class="mx-auto h-8 w-8"
                  src="~/assets/icons/category.svg"
                  alt=""
                />
                All Products</nuxt-link
              >
            </swiper-slide>
            <swiper-slide
              v-for="c in categories"
              class="flex flex-col justify-center border-b-[3px] border-transparent pt-4 text-center opacity-70 duration-200 hover:border-b-[3px] hover:border-black hover:opacity-100 hover:duration-200"
            >
              <nuxt-link
                :to="`/categories/${c}`"
                class="py-1 text-sm font-medium text-black"
              >
                <img
                  class="mx-auto h-8 w-8"
                  src="~/assets/icons/discount.svg"
                  alt=""
                />
                #{{ c }}</nuxt-link
              >
            </swiper-slide>
          </swiper>
          <!-- <ButtonFilter /> -->
        </div>
      </div>
    </div>
  </nav>
</template>

<style>
nav {
  z-index: 999;
}
</style>

<script>
import { Swiper, SwiperSlide } from 'swiper/vue';

// Import Swiper styles
import 'swiper/css';

import 'swiper/css/navigation';
// const { categories } = await useFetch(
//   'https://dummyjson.com/products/categories'
// );
// import required modules
import { Navigation } from 'swiper';

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const { data: categories } = useFetch(
      'https://dummyjson.com/products/categories'
    );
    return {
      modules: [Navigation],
      categories,
    };
  },
};
</script>

<!-- <script setup>
import { AdjustmentsHorizontalIcon } from '@heroicons/vue/24/solid';
</script> -->
<style>
.swiper-button-disabled {
  display: none;
}
</style>
